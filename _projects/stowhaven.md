---
layout: project
id: stowhaven
title: Stowhaven
summary: A low-cost, cloud-native backup platform
platform: .NET 10, Azure
logo: assets/images/projects/Stowhaven/ArchitecturePlaceholder.svg
date: 2026-08-17
start_date: 2025-09-07
ongoing: true
---

## Project Overview

**Stowhaven** is a cloud-native backup platform built with **.NET 10**, **Azure Container Apps**, **Dapr**, **Azure Blob Storage**, and **Azure Cosmos DB for NoSQL**. It is designed to keep the control plane small and inexpensive: the API coordinates each backup, but the client sends the actual file data directly to Blob Storage.

The repository contains the complete platform, including a public gateway, an internal API, a background worker, a cross-platform backup client, shared libraries, infrastructure-as-code, and the CI/CD workflow used to deploy it.

<div class="project-images">
  <img src="/assets/images/projects/Stowhaven/ArchitecturePlaceholder.svg" alt="Placeholder for the high-level Stowhaven architecture" class="project-image" />
  <p><b>Suggested main image:</b> A high-level architecture overview showing the client, gateway, API, queue, worker, Blob Storage, Cosmos DB, and Application Insights. The direct upload path to Blob Storage should be visually distinct from the control flow.</p>
</div>

---

## Architecture

The platform separates its responsibilities across three services:

- The **Gateway** authenticates public traffic, performs the Microsoft Entra ID on-behalf-of exchange, and forwards requests to the internal API.
- The **Backup API** handles device registration, backup runs, restore metadata, authorization, and short-lived upload permissions.
- The **Backup Worker** consumes queued commit events, validates staged files, moves active versions into place, retires older versions, and updates authoritative state.

This separation keeps large uploads away from the application services. After starting a run, the client receives a short-lived, directory-scoped User Delegation SAS and uploads new or changed files directly to Blob Storage. The API then publishes a commit event through a Dapr binding, allowing the worker to finish the run asynchronously.

---

## Security and Storage

The platform uses managed identities for access to Blob and Queue Storage, Cosmos DB, and Key Vault. Clients never receive storage account keys; they only receive least-privilege SAS URLs for their current run. The backup client can also encrypt files before upload, allowing an optional zero-knowledge workflow in which plaintext data never leaves the device.

Backups are incremental, so only new and changed files are uploaded. Active files are stored separately from staging data and retired versions. Azure lifecycle policies move committed backups through lower-cost storage tiers over time, while temporary staging data and expired versions can be cleaned up independently.

## Client and Operations

The .NET client scans configured targets, applies `.backupignore` rules, uploads files, and waits for commit completion. It supports interactive first-time configuration while keeping scheduled backup and restore runs silent. The Linux installer sets up a user-owned systemd timer, and the client is also suitable for Windows Task Scheduler.

For local development, Docker Compose starts the services alongside Dapr, Azurite, SQLite, and the Aspire dashboard. In production, Bicep defines the Azure resources and GitHub Actions validates, builds, publishes, and deploys the platform in phases. Application Insights and Log Analytics provide tracing and operational visibility.

---

## Reflection

This project started as a personal challenge to bring together the skills I had learned across application development, distributed systems, cloud infrastructure, security, and operations. I wanted to apply them in one complete project and find out whether I could build a cloud backup solution that cost less than the subscription I had been using.

That challenge succeeded. By keeping the control plane small and sending backup data directly to storage, I was able to build a solution with lower running costs while retaining control over its security and architecture. More importantly, the project gave me a practical way to turn skills learned across several areas into one end-to-end platform that solves a real problem for me.

### Source Code

The complete platform and its technical documentation are available on [GitHub](https://github.com/FlorisDeVries/backup-api).
