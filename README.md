# Magento 2 — B2B SDK Starter Kit

A starter for building B2B commerce on Magento 2, pre-wired with the [Orangecat B2B SDK](https://github.com/olivertar/m2_b2bsdk) and a Docker-based development environment via [graycoreio/magento2-devcontainer](https://github.com/graycoreio/magento2-devcontainer).

> **Starter kit, not a production store.** This is a learning and prototyping baseline. Going to production requires hosting, SSL, payments, performance tuning, and a security review.

## Requirements

- [Docker](https://www.docker.com/products/docker-desktop/) (4+ CPUs, 8 GB+ RAM allocated)
- [VS Code](https://code.visualstudio.com/) with the [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension
- **Magento Marketplace access keys** — required to download packages from `repo.magento.com`. Get them at [commercemarketplace.adobe.com](https://commercemarketplace.adobe.com/) → My Profile → Access Keys.

## Quickstart

1. **Clone the repository** with submodules:
   ```bash
   git clone --recurse-submodules https://github.com/olivertar/m2_b2bsdk_starterkit.git
   cd m2_b2bsdk_starterkit
   ```
2. **Create `auth.json`** in the project root with your Magento Marketplace keys:
   ```json
   {
       "http-basic": {
           "repo.magento.com": {
               "username": "<public-key>",
               "password": "<private-key>"
           }
       }
   }
   ```
   > This file is gitignored. Without it, `composer install` will be skipped and setup will not complete.
3. **Open in VS Code** and select **Reopen in Container** when prompted (or via the Command Palette: `Dev Containers: Reopen in Container`).
3. **Wait for setup** — the container will install Magento, enable all B2B SDK modules, and run the setup upgrade automatically.
4. **Access the storefront** at [http://localhost:8000](http://localhost:8000)
5. **Access the admin panel** at [http://localhost:8000/admin](http://localhost:8000/admin) — credentials: `admin` / `admin123`
6. **Check email** at [http://localhost:8025](http://localhost:8025) (Mailpit)

## What's Included

- **Magento Open Source 2.4.8-p5**
- **[Orangecat B2B SDK](https://orangecat.es/en/b2bsdk/)** (`orangecat/module-b2bsdk-installer`) — a suite of B2B modules ([docs](https://orangecat.es/en/b2bsdk/) · [repo](https://github.com/olivertar/m2_b2bsdk)):
  - Company management and customer approval
  - Company-specific credit and payment methods
  - Sales representative assignment
  - Customer-specific and company-specific pricing
  - Price list management
  - Saved product lists / order templates
  - Purchase order workflows
  - Bulk SKU ordering
  - Return / RMA management
  - Content visibility rules per customer group
- **[graycoreio/magento2-devcontainer](https://github.com/graycoreio/magento2-devcontainer)** — production-parity Docker environment
- **Full service stack** — Nginx, MySQL, Redis, OpenSearch, RabbitMQ

## Services & Ports

| Service    | Port | URL                                           |
|------------|------|-----------------------------------------------|
| Storefront | 8000 | [http://localhost:8000](http://localhost:8000) |
| Admin      | 8000 | [http://localhost:8000/admin](http://localhost:8000/admin) |
| Mailpit    | 8025 | [http://localhost:8025](http://localhost:8025) |
| MySQL      | 3306 | —                                             |
| OpenSearch | 9200 | —                                             |
| RabbitMQ   | 5672 | —                                             |
| Redis      | 6379 | —                                             |

## Related Projects

- [graycoreio/magento2-devcontainer](https://github.com/graycoreio/magento2-devcontainer) — the devcontainer powering this environment
- [olivertar/m2_b2bsdk](https://github.com/olivertar/m2_b2bsdk) — B2B SDK repository
- [orangecat.es/en/b2bsdk](https://orangecat.es/en/b2bsdk/) — B2B SDK landing page and documentation

---

**Note:** Magento® is a registered trademark of Adobe Inc. This project is not affiliated with or endorsed by Adobe.
