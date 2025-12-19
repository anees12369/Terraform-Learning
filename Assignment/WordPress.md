**Deploying WordPress via Terraform**
---

**What is WordPress?**
---
- WordPress is a content management system (CMS).  
- It's software that makes it easy to **create, manage, and publish content on the web** — like blogs, websites, or even e-commerce sites without needing to build everything from scratch.

**A few key points:**
---
- It’s PHP-based – the application code runs on a web server (like Apache or Nginx).

- It needs a database – typically MySQL or MariaDB, to store posts, pages, users, settings, etc.

- It serves web pages – visitors access it via a browser.

- So in your Terraform setup: **EC2 runs the PHP WordPress app, RDS stores the data, and the domain points users to it.**

