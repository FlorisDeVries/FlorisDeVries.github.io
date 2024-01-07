# Project Setup Guide for Windows

This README provides a step-by-step guide on how to set up a local environment on a clean Windows installation using Chocolatey.

## Prerequisites

- A clean installation of Windows.
- Chocolatey package manager installed. If not already installed, follow the instructions at [Chocolatey Installation Guide](https://chocolatey.org/install).

## Step-by-Step Setup

### 1. Install Ruby

Jekyll requires Ruby to run. We'll use Chocolatey to install Ruby.

```powershell
choco install ruby -y
```

After installation, restart your command prompt or PowerShell to refresh the environment variables.

### 2. Install Bundler and Jekyll
Bundler manages Ruby gem dependencies, and Jekyll is the static site generator used.

``` powershell
gem install jekyll bundler
```

### 3. Install dependencies
Navigate to your project directory and install dependencies.

``` powershell
bundle install
```

### 4. Run server locally
Start the jekyll server

``` powershell
bundle exec jekyll serve
```