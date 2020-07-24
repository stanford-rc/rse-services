---
title: Risk Classification
---

# Risk Classification

Whenever you need to deploy documentation, a tool, or a site, you need to consider the 
<a href="https://uit.stanford.edu/guide/securitystandards" target="_blank">Stanford Security Standards</a>
and ensure that your application, tool, or resource meets all requirements.

{% include alert.html title="Stanford Minimum Security Requirements" type="warning" content="We take security very seriously at Stanford. You should not deploy an application that you are unsure about the risk level. Low and medium risk must comply with <a href='https://uit.stanford.edu/guide/securitystandards/' target='_blank'>Stanford Security Standards</a>. High risk data must always be approved in advance. Read the sections below for more details." %}


## Low or Moderate Risk

For the low or moderate risk levels, if you are deploying something on your own you don't
need strict approval, although we do suggest recruiting multipe parties to look over
the deployment to be extra sure that you've categorized it correctly and not missed any detail.
However you **do** need to ensure that: 

 - All *applications* must comply with [security application standards](https://uit.stanford.edu/guide/securitystandards#security-standards-applications)
 - All *cloud infrastructure* must comply with [software as a service standards](https://uit.stanford.edu/guide/securitystandards/saas_paas) or [infrastructure as a service](https://uit.stanford.edu/guide/securitystandards/iaas) standards. 
 - Desktop applications, endpoints, or other kinds of resources that don't fit into the above categories also have requirements, and you should consult [Stanford Security Standards](https://uit.stanford.edu/guide/securitystandards/) for more details.

These rules apply to anyone at Stanford who is deploying local or cloud infrastructure. Whether you are faculty, staff, or student,
the rules apply for you.

## High Risk

For high risk data, you are not allowed to deploy resources, services, or any kind of infrastructure on your own.
These projects that use high risk data or resources have a formal ISO and Privacy review that must be completed.
Please submit a [help request](https://uit.stanford.edu/guide/securitystandards#questions) to ISO if you have
any inquiries, or [ask us at RSE Services](/support).
