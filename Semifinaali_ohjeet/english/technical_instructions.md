# Instructions

(updated 27.1.)

## Important information about changes to the instructions

- Unlike last year, only **one repository** is used and deployed this year. Last year there were separate repositories for backend and frontend. This was not problem-free for everyone, so this year only one repository is used.
- It is the competitor’s responsibility to configure their project so that separate repositories for backend and frontend are **not required**.
  - If you for example want to merge the excisting Laravel and React-vite templates, it has to be done yourself eg. build a dist in the react project and copy it into the laravel project.

> _I apologize that it took this long to provide up-to-date instructions. Issues in the deployment pipeline and repository mapping prevented me from updating the instructions earlier, as my own environment was not working either.
> – Laura / semifinal coordinator_

## Credentials and addresses

- All required usernames, passwords, access codes, and URLs can be found in the **Competitor Credentials** document sent to competitors. The same information is also available in the Dashboard.

- The same credentials are used **before the competition and during the competition**.

## Dashboard (Competitor Dashboard)

- You can access all services required during the competition via the
  [Competitor Dashboard](https://mc.nstrim.io/cd)

- The **6-digit access code** required to log in can be found in the Competitor Credentials document.

### In the Dashboard you can:

- See how much competition time remains
- Find the link to the website where your project is deployed
- Find a link to the Gitea service
- Find a link to the phpMyAdmin service
- Find a link to the [instructions and documentation](https://mc.nstrim.io/docs/competitor)
- Perform repository mapping, i.e. select which repository is deployed

---

## Project start and deployment in a nutshell

- Create a repository from a template
- Clone the repository
- No changes to the code are required
- Push the first commit from your local environment
- Go to the Dashboard
- Connect the module to the new repository (module mapping)
- The application works

---

### 1. Creating a repository

- Open the Git service (the link can be found in the Competitor Dashboard):
  [https://git.taitaja2026.nstrim.app/](https://git.taitaja2026.nstrim.app/)
- Log in using the credentials found in the Competitor Dashboard.
- Create a new repository from a ready-made template (framework or “vanilla”).

![new repo](/img/orgs.png)

- Name the repository as you wish:
  - use **lowercase letters only**
  - no spaces

- Under **Template items**, select:
  - ☑ **Git content (Default Branch)**

![new repo](/img/new_repo.png)

The templates include the required configuration for automatic deployment.

---

### 2. Cloning the repository and development

**Clone the repository:**

- Copy the repository URL from the Gitea user interface:

![git clone](/img/clone.png)

- Clone the repository to your local machine

**Coding:**

- Make changes locally
- Commit regularly (frequently)
- Update the README file if necessary (installation instructions, dependencies)

---

### 3. Repository mapping (required)

⚠️ **This step is required for your site to be deployed**

- Open the Competitor Dashboard
- Select the correct repository from the list of repositories in your Gitea account
- Save the selection

![Repository mapping](/img/select_repo.png)

Without repository mapping, your work **will not be deployed automatically**, even if the push succeeds.

---

### 4. Automatic deployment and publishing

- Every Git push triggers an automatic deployment

- The deployment process takes a moment:
  - for example, Next.js and Laravel may take up to approximately 2 minutes

- You can view the deployment status in the **Gitea Actions** tab
  ![workflows](/img/status.png)

**Where the project is deployed:** The competition URL can be found in the Dashboard under **Module Work URL**

![module url](/img/url.png)

**Recommendations:**

- Commit frequently, but push only when a larger feature is ready.
- Always check the deployment status before continuing.
- Make sure your final push is completed before the module time limit expires.

---

## Connecting to the database – using phpMyAdmin

You can easily access the service via the **Dashboard**.

**Login:**

- Click the MySQL icon in the Dashboard, which takes you to:
  [https://pma.taitaja2026.nstrim.app](https://pma.taitaja2026.nstrim.app)
- Log in using the credentials found in the Competitor Dashboard.

**Database connection in the application:**

```php
define('DB_HOST', 'db.taitaja2026.nstrim.app');
```

The database username and password can be found in the Competitor Dashboard.

---
