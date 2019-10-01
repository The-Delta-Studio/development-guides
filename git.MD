# Version Control

Simple version control guideline

## Contents

- [Version Control](#version-control)
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
        <td>project acronym - api - action</td> 
        <td><code>via-api-scrape</code></td>
    </tr>
    <tr>
        <td>Service</td>
        <td>project acronym - service - action</td> 
        <td><code>via-service-auth</code></td>
    </tr>
    <tr>
        <td>Web App</td>
        <td>project acronym - app - web</td> 
        <td><code>via-app-web</code></td>
    </tr>
    <tr>
        <td>Admin App</td>
        <td>project acronym - app - admin</td> 
        <td><code>via-app-admin</code></td>
    </tr>
    <tr>
        <td>Marketing Web App</td>
        <td>project acronym - app - marketing</td> 
        <td><code>via-app-marketing</code></td>
    </tr>
    <tr>
        <td>Web Extension</td>
        <td>project acronym - web - ext</td> 
        <td><code>via-web-ext</code></td>
    </tr>
    <tr>
        <td>Mobile App</td>
        <td>project acronym - mob - type</td> 
        <td>
            <code>via-mob-rn</code>
            <code>via-mob-android</code>
            <code>via-mob-ios</code>
            <code>via-mob-pwa</code>
        </td>
    </tr>
    <tr>
        <td>Serverless</td>
        <td>project acronym - func - action</td> 
        <td><code>via-func-email</code></td>
    </tr>
    <tr>
        <td>Template</td>
        <td>framework - action (if applicable) - type - template</td> 
        <td>
            <code>rn-mob-template</code>
            <code>react-web-app-template</code>
            <code>gatsby-marketing-app-template</code>
            <code>dotnet-service-template</code>
            <code>dotnet-api-template</code>
            <code>node-func-template</code>
        </td>
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

