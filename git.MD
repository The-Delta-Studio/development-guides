# Source Control

Simple version control guideline

## Contents

- [Source Control](#source-control)
  - [Contents](#contents)
  - [Repository](#repository)
  - [Branching](#branching)
  - [Versioning](#versioning)
  - [PR](#pr)

## Repository

> Naming convention for repositories

Repositories follows the following guidelines:

<table width="80%">
    <tr>
        <th>Type</th>
        <th>Guideline</th> 
        <th>Example</th>
    </tr>
    <tr>
        <td>API</td>
        <td>project acronym - action - api</td> 
        <td><code>via-scrape-api</code></td>
    </tr>
    <tr>
        <td>Service</td>
        <td>project acronym - action - service</td> 
        <td><code>via-auth-service</code></td>
    </tr>
    <tr>
        <td>Web App</td>
        <td>project acronym - web - app</td> 
        <td><code>via-web-app</code></td>
    </tr>
    <tr>
        <td>Admin App</td>
        <td>project acronym - admin - app</td> 
        <td><code>via-admin-app</code></td>
    </tr>
    <tr>
        <td>Marketing Web App</td>
        <td>project acronym - marketing - app</td> 
        <td><code>via-marketing-app</code></td>
    </tr>
    <tr>
        <td>Mobile App</td>
        <td>project acronym - type - mob</td> 
        <td>
            <code>via-rn-mob</code>
            <code>via-android-mob</code>
            <code>via-ios-mob</code>
        </td>
    </tr>
    <tr>
        <td>Serverless</td>
        <td>project acronym - action - func</td> 
        <td><code>via-email-func</code></td>
    </tr>
</table>

## Branching

> Branching naming conventions and release strategies

<table width="80%">
    <tr>
        <th>Type</th>
        <th>Guideline</th>
        <th>Description</th>
        <th>Branch from</th>
        <th>Example</th>
    </tr>
    <tr>
        <td>Feature</td>
        <td>feature/ticket-number</td>
        <td>A branch for the development of a new feature</td>
        <td><code>develop</code></td>
        <td><code>feature/VIA-181</code></td>
    </tr>
    <tr>
        <td>Bugfix</td>
        <td>fix/ticket-number</td>
        <td>A branch for bugfixes</td>
        <td>
            <code>develop</code>
            <code>staging</code>
        </td>
        <td><code>fix/VIA-192</code></td>
    </tr>
    <tr>
        <td>Chore</td>
        <td>chore/ticket-number</td>
        <td>Good common housekeeping of repository</td>
        <td><code>develop</code></td>
        <td><code>chore/VIA-200</code></td>
    </tr>
    <tr>
        <td>Hotfix</td>
        <td>hotfix/ticket-number</td>
        <td>Hotfixes after production release</td>
        <td><code>master</code></td>
        <td><code>hotfix/VIA-94</code></td>
    </tr>
     <tr>
        <td>Release preparation</td>
        <td>staging/ticket-number</td>
        <td>Preparing develop for release</td>
        <td><code>develop</code></td>
        <td><code>staging/VIA-11</code></td>
    </tr>
</table>

## Versioning

> Release versioning

## PR

> Pull requests, commit messages, commit sizes, reviewers and code checks

