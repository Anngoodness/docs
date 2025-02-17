---
title: About alerts for vulnerable dependencies
intro: '{% data variables.product.product_name %} sends {% ifversion ghes %}{% data variables.product.prodname_dependabot_alerts %}{% else %}security alerts{% endif %} when we detect vulnerabilities affecting your repository.'
versions:
  ghes: <=2.22
topics:
  - Security
redirect_from:
  - /github/managing-security-vulnerabilities/about-alerts-for-vulnerable-dependencies
shortTitle: Dependabot alerts
---

<!--See /content/code-security/supply-chain-security/about-alerts-for-vulnerable-dependencies for the current version of this article -->

## About vulnerable dependencies

{% data reusables.repositories.a-vulnerability-is %}

When your code depends on a package that has a security vulnerability, this vulnerable dependency can cause a range of problems for your project or the people who use it.

## Detection of vulnerable dependencies

 {% ifversion ghes %}{% data variables.product.prodname_dependabot %} detects vulnerable dependencies and sends {% data variables.product.prodname_dependabot_alerts %}{% else %}{% data variables.product.product_name %} detects vulnerable dependencies and sends security alerts{% endif %} when:

- New advisory data is synchronized to {% data variables.product.prodname_ghe_server %} each hour from {% data variables.product.prodname_dotcom_the_website %}. {% data reusables.security-advisory.link-browsing-advisory-db %}
- The dependency graph for a repository changes. For example, when a contributor pushes a commit to change the packages or versions it depends on. For more information, see "[About the dependency graph](/github/visualizing-repository-data-with-graphs/about-the-dependency-graph)."

{% data reusables.repositories.dependency-review %}

For a list of the ecosystems that {% data variables.product.product_name %} can detect vulnerabilities and dependencies for, see "[Supported package ecosystems](/github/visualizing-repository-data-with-graphs/about-the-dependency-graph#supported-package-ecosystems)."

{% note %}

**Note:** It is important to keep your manifest and lock files up to date. If the dependency graph doesn't accurately reflect your current dependencies and versions, then you could miss alerts for vulnerable dependencies that you use. You may also get alerts for dependencies that you no longer use.

{% endnote %}

{% ifversion ghes %}
## {% data variables.product.prodname_dependabot %} alerts for vulnerable dependencies
{% else %}
## Sicherheitsmeldungen für angreifbare Abhängigkeiten
{% endif %}

{% data reusables.repositories.enable-security-alerts %}

{% ifversion ghes %}
When {% data variables.product.product_name %} identifies a vulnerable dependency, we generate a {% data variables.product.prodname_dependabot %} alert and display it on the Security tab for the repository. The alert includes a link to the affected file in the project, and information about a fixed version. {% data variables.product.product_name %} also notifies the maintainers of affected repositories about the new alert according to their notification preferences. For more information, see "[Configuring notifications for vulnerable dependencies](/github/managing-security-vulnerabilities/configuring-notifications-for-vulnerable-dependencies)."
{% endif %}

{% warning %}

**Note**: {% data variables.product.product_name %}'s security features do not claim to catch all vulnerabilities. Though we are always trying to update our vulnerability database and generate alerts with our most up-to-date information, we will not be able to catch everything or tell you about known vulnerabilities within a guaranteed time frame. Diese Funktionen ersetzen nicht die menschliche Überprüfung jeder Abhängigkeit auf potenzielle Sicherheitsrisiken oder andere Probleme. Daher empfehlen wir, einen Sicherheitsdienst zu konsultieren oder bei Bedarf eine gründliche Überprüfung der Sicherheitsrisiken durchzuführen.

{% endwarning %}

## Access to {% ifversion ghes %}{% data variables.product.prodname_dependabot %}{% else %}security{% endif %} alerts

You can see all of the alerts that affect a particular project in the repository's dependency graph.

{% ifversion ghes %}
By default, we notify people with admin permissions in the affected repositories about new {% data variables.product.prodname_dependabot_alerts %}.{% endif %}


{% data reusables.notifications.vulnerable-dependency-notification-delivery-method-customization %}{% ifversion ghes %} For more information, see "[Configuring notifications for vulnerable dependencies](/github/managing-security-vulnerabilities/configuring-notifications-for-vulnerable-dependencies)."{% endif %}
