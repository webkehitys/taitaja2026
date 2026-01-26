# Instructions

## NSTRIM system documentation

**The service's own documentation can be found at https://mc.nstrim.io/docs/competitor and it is very helpful.**

If the instructions in the documentation conflict with the instructions below, the system documentation is more likely to be correct. We are working to clarify the usage instructions so that the deployment process will succeed more reliably.

## Quick Overview

1. Create a repository using the provided templates at [https://git.taitaja2026.nstrim.app/](https://git.taitaja2026.nstrim.app/). It is important to use the given templates as they include Gitea Actions functionality and will automatically deploy your work upon push.
2. Clone the project and work locally. Commit frequently but only push when a larger feature is ready. Each push takes time to deploy (e.g., Next.js and Laravel up to 2 minutes). Be patient.
3. You can use phpMyAdmin at [pma.taitaja2026.nstrim.app](pma.taitaja2026.nstrim.app).

---

## 1. Create a New Repository

- Go to the Git server: [https://git.taitaja2026.nstrim.app/](https://git.taitaja2026.nstrim.app/).
- Log in with your username and password.
- Navigate to **Organization → Frameworks**.

  ![orgs](/img/orgs.png)

- Select the framework you want to use or the "vanilla" template.
- Click **"Use this template"** to create a new repository.
- Name the repository according to the module name: **frontend** or **backend**. For vanilla projects, name the repository **frontend**.

  ![secrets settings](/img/new_repo.png)

- Open your repository settings: **Settings → Actions → Secrets**.
- Add the following:
  - **USER:** Your username (e.g., comp01)
  - **PASS:** Your password (e.g., test123)

  ![secrets settings](/img/add-secret.png)

  ![secrets settings](/img/secrets.png)

- Commit and verify that Gitea Actions is working correctly.
- Check your changes at the URL:

  ```
  https://<subdomain>-<module_name>.taitaja.webkehitys.fi
  ```

> Each competitor is assigned a username, password, and alias.
> The alias forms the subdomain address used in the competition environment.
>
> For example, alias **`skdjf`** appears as:
>
> - Frontend: https://skdjf-frontend.taitaja2026.nstrim.app/
> - Backend: https://skdjf-backend.taitaja2026.nstrim.app/

---

## 2. Clone the Repository and Work

**Clone the repository:**

- Use the repository URL to clone:

  ```bash
  git clone https://git.taitaja2026.nstrim.app//<username>/<module_name>.git
  ```

  **Example:**

  ```bash
  git clone https://git.taitaja2026.nstrim.app//comp01/frontend.git
  ```

**Edit, commit, and develop:**

- Commit regularly to keep your work organized.
- Update the **README file** with important information like installation instructions and dependencies.

---

## 3. Using phpMyAdmin

**Access phpMyAdmin:**

- Go to [pma.taitaja2026.nstrim.app](pma.taitaja2026.nstrim.app).
- Log in with your username and password.

**Database connection:**

- Use the following host setting to connect to the database:

  ```php
  define('DB_HOST', 'db.taitaja.webkehitys.fi');
  ```

Each user has predefined databases:

```
username_frontend
username_backend
```

**Example:**

```
comp01_frontend
comp02_backend
```

---

## 4. Automation and Deployment

- Each **push** automatically deploys to the competition URL:

  ```
  https://<subdomain>-<module_name>.taitaja2026.nstrim.app/
  ```

- Since each Git push triggers a deployment process that takes time and uses resources, we recommend grouping changes and pushing them less frequently.
- Check your changes at the competition URL after each push.

---

> Each student is assigned a username, password, and alias.
> The alias forms the subdomain address used in the competition environment.
>
> For example, alias **`skdjf`** appears as:
>
> - Frontend: https://skdjf-frontend.taitaja2026.nstrim.app/
> - Backend: https://skdjf-backend.taitaja2026.nstrim.app/
