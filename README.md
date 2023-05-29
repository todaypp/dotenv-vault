# dotenv-vault [![NPM Version](https://img.shields.io/npm/v/dotenv-vault.svg?style=flat-square)](https://npmjs.org/package/dotenv-vault)

<img src="https://raw.githubusercontent.com/motdotla/dotenv/master/dotenv.svg" alt="dotenv-vault" align="right" width="200" />

Manage your secrets using dotenv-vault's all-in-one toolkit. Say goodbye to scattered secrets across multiple platforms and tools. The #1 secrets manager for .env files.

Deploy your secrets anywhere with modern encryption and sync your .env files with a single command.

* [🌱 Install](#-install)
* [🏗️ Usage](#%EF%B8%8F-usage)
* [🚀 Deploying](#-deploying)
* [🌴 Multiple Environments](#-manage-multiple-environments)
* [📚 Examples](#-examples)
* [📖 Commands](#-commands)
* [❓ FAQ](#-faq)

## 🌱 Install

<h4><img alt="apple icon" src="https://api.iconify.design/mdi/apple.svg" width="40" /></h4>

Install via [Homebrew](https://github.com/dotenv-org/homebrew-brew)

```shell
$ brew install dotenv-org/brew/dotenv-vault
$ dotenv-vault help
```

<h4><img alt="windows icon" src="https://api.iconify.design/mdi/windows.svg" width="40" /></h4>

Install on [Windows](https://dotenv-vault-assets.dotenv.org/)

* [32-bit installer](https://dotenv-vault-assets.dotenv.org/channels/stable/dotenv-vault-x86.exe)
* [64-bit installer](https://dotenv-vault-assets.dotenv.org/channels/stable/dotenv-vault-x64.exe)

<h4><img alt="docker icon" src="https://api.iconify.design/mdi/docker.svg" width="40" /></h4>

Install and run commands via [Docker](https://hub.docker.com/r/dotenv/dotenv-vault)

```shell
$ docker run -w $(pwd) -v $(pwd):$(pwd) -it dotenv/dotenv-vault help
```

<h4><img alt="npm icon" src="https://api.iconify.design/fontisto/npm.svg" width="40" /></h4>

Install and run commands via [npx](https://docs.npmjs.com/cli/v7/commands/npx)

```shell
$ npx dotenv-vault help
```

<sub>>>> More details at <a href="https://www.dotenv.org/install/">www.dotenv.org/install</a></sub>

## 🏗️ Usage

Push your `.env` file.

```bash
$ dotenv-vault push
```

Commit your `.env.vault` file safely to code.

```bash
$ git add .env.vault
$ git commit -am "Add .env.vault"
$ git push
```

Pull the latest `.env` changes.

```bash
$ git pull
$ dotenv-vault pull
```

That's it! You securely backed-up and synced your `.env` file.

<sub>>>> More details on <a href="https://www.dotenv.org/docs/quickstart?r=1">quickstart ⚡️ guide</a></sub>

## 🚀 Deploying

Encrypt your `.env.vault` file.

```bash
$ dotenv-vault build
```

Fetch your production `DOTENV_KEY`.

```bash
$ dotenv-vault keys production
remote:   Listing .env.vault decryption keys... done
dotenv://:key_1234…@dotenv.org/vault/.env.vault?environment=production
```

Set `DOTENV_KEY` on your server.

```bash
# heroku example
heroku config:set DOTENV_KEY=dotenv://:key_1234…@dotenv.org/vault/.env.vault?environment=production
```

Commit your `.env.vault` file safely to code and deploy.

```bash
$ git add .env.vault
$ git commit -am "Update .env.vault"
$ git push
$ git push heroku main # heroku example
```

That's it! On deploy, your `.env.vault` file will be decrypted and its secrets injected as environment variables – just in time.

<sub>>>> More details toward end of <a href="https://www.dotenv.org/docs/quickstart?r=1">quickstart ⚡️ guide</a></sub>

## 🌴 Manage Multiple Environments

Sync your `.env` file. Run the push command and follow the instructions. [learn more](/docs/sync/quickstart)

```
$ dotenv-vault push
```

After you've pushed your `.env` file, dotenv-vault automatically sets up multiple environments. Manage multiple environments with the included UI. [learn more](/docs/tutorials/environments)

```
$ dotenv-vault open
```

That's it! Manage your ci, staging, and production secrets from there. Rebuild your `.env.vault` file and redeploy when ready.


Would you also like to pull your production `.env` to your machine? Run the command:

```
$ dotenv-vault pull production
```

<sub>>>> More details at <a href="https://www.dotenv.org/docs/tutorials/environments?r=1">www.dotenv.org/docs/tutorials/environments</a></sub>

---

ℹ️ The above is **🔐 Vault Managed**. If you would prefer to use **💻 Locally Managed** environments and deploys, [see the faq below](#how-do-i-use--locally-managed-dotenv-vault).

## 📚 Examples

<table>
  <tbody>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/vercel/nodejs?r=1">
          <img src="https://api.iconify.design/devicon/vercel.svg" alt="Vercel", width="20" />
          Vercel
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/heroku/rails">
          <img src="https://api.iconify.design/skill-icons/heroku.svg" alt="Heroku", width="20" />
          Heroku
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/github/actions-nextjs">
          <img src="https://api.iconify.design/devicon/github.svg" alt="GitHub", width="20" />
          GitHub Actions
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/gitlab/ci-quickstart">
          <img src="https://api.iconify.design/devicon/gitlab.svg" alt="GitLab", width="20" />
          GitLab CI/CD
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/netlify/astro?r=1">
          <img src="https://api.iconify.design/skill-icons/netlify-light.svg" alt="Netlify", width="20" />
          Netlify
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/docker/express?r=1">
          <img src="https://api.iconify.design/skill-icons/docker.svg" alt="Docker", width="20" />
          Docker
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/docker-compose/express?r=1">
          <img src="https://api.iconify.design/skill-icons/docker.svg" alt="Docker Compose", width="20" />
          Docker Compose
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/circleci/rails?r=1">
          <img src="https://api.iconify.design/logos/circleci.svg" alt="CircleCI", width="20" />
          CircleCI
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/serverless/express?r=1">
          <img src="https://api.iconify.design/logos/serverless.svg" alt="Serverless", width="20" />
          Serverless
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/railway/express?r=1">
          <img src="https://api.iconify.design/simple-icons/railway.svg" alt="Railway", width="20" />
          Railway
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/render/express?r=1">
          <img src="https://api.iconify.design/simple-icons/render.svg" alt="Render", width="20" />
          Render
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/travis-ci/nodejs?r=1">
          <img src="https://api.iconify.design/simple-icons/travisci.svg" alt="Travis CI", width="20" />
          Travis CI
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/google-cloud/nodejs?r=1">
          <img src="https://api.iconify.design/devicon/googlecloud.svg" alt="Google Cloud", width="20" />
          Google Cloud
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/fly/express?r=1">
          <img src="https://api.iconify.design/logos/fly-icon.svg" alt="Fly.io", width="20" />
          Fly.io
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/integrations/slack?r=1">
          <img src="https://api.iconify.design/devicon/slack.svg" alt="dotenv-vault + Slack", width="20" />
          Slack
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/buddy/nodejs?r=1">
          <img src="https://api.iconify.design/logos/buddy.svg" alt="Buddy", width="20" />
          Buddy
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/cloud66/nodejs?r=1">
          <img src="https://api.iconify.design/simple-icons/cloud66.svg" alt="Cloud66", width="20" />
          Cloud66
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/digital-ocean/nodejs?r=1">
          <img src="https://api.iconify.design/devicon/digitalocean.svg" alt="Digital Ocean", width="20" />
          Digital Ocean
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/dagger/nodejs?r=1">
          <img src="https://dagger.io/img/logo-alt-2.svg" alt="Dagger", width="20" />
          Dagger
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/bitbucket/nodejs?r=1">
          <img src="https://api.iconify.design/devicon/bitbucket.svg" alt="Bitbucket", width="20" />
          Bitbucket
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/railway/nodejs?r=1">
          <img src="https://api.iconify.design/devicon/nodejs.svg" alt="Node.js", width="20" />
          Node.js
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/vercel/pnpm?r=1">
          <img src="https://api.iconify.design/devicon/pnpm.svg" alt="Pnpm", width="20" />
          pnpm
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/vercel/express?r=1">
          <img src="https://api.iconify.design/devicon/express.svg" alt="Express", width="20" />
          Express
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/github/actions-nextjs?r=1">
          <img src="https://api.iconify.design/devicon/nextjs.svg" alt="NextJS", width="20" />
          NextJS
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/github/actions-remix?r=1">
          <img src="https://api.iconify.design/skill-icons/remix-dark.svg" alt="Remix", width="20" />
          Remix
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/netlify/astro?r=1">
          <img src="https://api.iconify.design/devicon/astro.svg" alt="Astro", width="20" />
          Astro
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/docker/rails?r=1">
          <img src="https://api.iconify.design/logos/rails.svg" alt="Rails", width="20" />
          Rails
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/heroku/sinatra?r=1">
          <img src="https://api.iconify.design/logos/ruby.svg" alt="Ruby", width="20" />
          Ruby
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/heroku/sinatra?r=1">
          <img src="https://api.iconify.design/logos/sinatra.svg" alt="Sinatra", width="20" />
          Sinatra
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/heroku/flask?r=1">
          <img src="https://api.iconify.design/devicon/flask.svg" alt="Flask", width="20" />
          Flask
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/heroku/flask?r=1">
          <img src="https://api.iconify.design/devicon/python.svg" alt="Python", width="20" />
          Python
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/supabase/nodejs?r=1">
          <img src="https://api.iconify.design/devicon/supabase.svg" alt="Supabase", width="20" />
          Supabase
        </a>
      </td>
    </tr>
    <tr>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/pulumi/nodejs?r=1">
          <img src="https://api.iconify.design/vscode-icons/file-type-pulumi.svg" alt="Pulumi", width="20" />
          Pulumi
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/vercel/angular?r=1">
          <img src="https://api.iconify.design/devicon/angular.svg" alt="Angular", width="20" />
          Angular
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/vercel/nuxt?r=1">
          <img src="https://api.iconify.design/logos/nuxt-icon.svg" alt="Nuxt", width="20" />
          Nuxt
        </a>
      </td>
      <td align="left" valign="middle">
        <a href="https://www.dotenv.org/docs/integrations/vercel/vite?r=1">
          <img src="https://api.iconify.design/devicon/vite.svg" alt="Vite", width="20" />
          Vite
        </a>
      </td>
    </tr>
  </tbody>
</table>

<sub>>>> More examples at <a href="https://www.dotenv.org/docs/tutorials/integrations?r=1">dotenv.org/docs/tutorials/integrations</a></sub>

## 📖 Commands

<sub>>>> More details at <a href="https://dotenv.org/docs">www.dotenv.org/docs</a></sub>

```
$ dotenv-vault help
```

* [new](#new)
* [login](#login)
* [logout](#logout)
* [push](#push)
* [pull](#pull)
* [open](#open)
* [whoami](#whoami)
* [build](#build)
* [keys](#keys)
* [rotatekey](#rotatekey)
* [decrypt](#decrypt)
* [versions](#versions)
* [local](#local-build)
  * [local build](#local-build)   
  * [local decrypt](#local-decrypt)   
  * [local keys](#local-keys)   

### `new`

Create your project at Dotenv Vault.

Example:

```bash
$ npx dotenv-vault new
```

##### ARGUMENTS

*[DOTENV_VAULT]*

Set .env.vault identifier. Defaults to generated value.

```
$ npx dotenv-vault new vlt_6beaae5…
local:    Adding .env.vault (DOTENV_VAULT)... done
local:    Added to .env.vault (DOTENV_VAULT=vlt_6beaa...)
```

##### FLAGS

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

---

### `login`

Log in to dotenv-vault.

Example:

```bash
$ npx dotenv-vault login
```

##### ARGUMENTS

*[DOTENV_ME]*

Set .env.me identifier. Defaults to generated value.

```
$ npx dotenv-vault login me_00c7fa…
```

##### FLAGS

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault login -y
```

---

### `logout`

Log out of dotenv-vault.

Example:

```bash
$ npx dotenv-vault logout
```

##### FLAGS

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault logout -y
```

---

### `push`

Push `.env` securely.

Example:

```bash
$ npx dotenv-vault push
```

##### ARGUMENTS

*[ENVIRONMENT]*

Set environment to push to. Defaults to development

```
$ npx dotenv-vault push production
```

*[FILENAME]*

Set input filename. Defaults to .env for development and .env.{environment} for other environments

```
$ npx dotenv-vault push production .env.production
```

##### FLAGS

*-m, --dotenvMe*

Pass .env.me (DOTENV_ME) credential directly (rather than reading from .env.me file)

```
$ npx dotenv-vault push --dotenvMe=me_b1831e…
```

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault push -y
```

---

### `pull`

Pull `.env` securely.

Example:

```bash
$ npx dotenv-vault pull
```

##### ARGUMENTS

*[ENVIRONMENT]*

Set environment to pull from. Defaults to development

```
$ npx dotenv-vault pull production
```

*[FILENAME]*

Set output filename. Defaults to .env for development and .env.{environment} for other environments

```
$ npx dotenv-vault pull production .env.production
```

##### FLAGS

*-m, --dotenvMe*

Pass .env.me (DOTENV_ME) credential directly (rather than reading from .env.me file)

```
$ npx dotenv-vault pull --dotenvMe=me_b1831e…
```

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault pull -y
```

If you want to pull a specific version you can do so. For example,

```
npx dotenv-vault pull development@v14
```

---

### `open`

Open project page.

Example:

```bash
$ npx dotenv-vault open
```

##### ARGUMENTS

*[ENVIRONMENT]*

Set environment to open to. Defaults to development.

```
$ npx dotenv-vault open production
```

##### FLAGS

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault open -y
```

---

### `whoami`

Display the current logged in user.

Example:

```bash
$ npx dotenv-vault whoami
```

##### FLAGS

*-m, --dotenvMe*

Pass .env.me (DOTENV_ME) credential directly (rather than reading from .env.me file)

```
$ npx dotenv-vault whoami dotenvMe=me_b1831e…
```

---

### `build`

Build .env.vault file.

Example:

```bash
$ npx dotenv-vault build
```

##### FLAGS

*-m, --dotenvMe*

Pass .env.me (DOTENV_ME) credential directly (rather than reading from .env.me file)

```
$ npx dotenv-vault build dotenvMe=me_b1831e…
```

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault build -y
```

---

### `keys`

List .env.vault decryption keys.

Example:

```bash
$ npx dotenv-vault keys
```

##### ARGUMENTS

*[ENVIRONMENT]*

Set environment. Defaults to all.

```
$ npx dotenv-vault keys production…
remote:   Listing .env.vault decryption keys... done
dotenv://:key_899..@dotenv.org/vault/.env.vault?environment=production
```

##### FLAGS

*-m, --dotenvMe*

Pass .env.me (DOTENV_ME) credential directly (rather than reading from .env.me file)

```
$ npx dotenv-vault keys dotenvMe=me_b1831e…
```

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault keys -y
```

---

### `rotatekey`

Rotate DOTENV_KEY.

Example:

```bash
$ npx dotenv-vault rotatekey production
```

##### FLAGS

*-m, --dotenvMe*

Pass .env.me (DOTENV_ME) credential directly (rather than reading from .env.me file)

```
$ npx dotenv-vault rotatekey dotenvMe=me_b1831e…
```

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault rotatekey -y
```

---

### `decrypt`

Decrypt .env.vault locally.

Example:

```bash
$ npx dotenv-vault decrypt dotenv://:key_1234@dotenv.org/vault/.env.vault?environment=development
```

##### ARGUMENTS

*[DOTENV_KEY]*

Set `DOTENV_KEY` to decrypt .env.vault. Development key will decrypt development, production will decrypt production, and so on.

```
$ npx dotenv-vault decrypt dotenv://:key_1234@dotenv.org/vault/.env.vault?environment=development
```

---

### `versions`

List version history.

Example:

```bash
$ npx dotenv-vault versions
```

##### ARGUMENTS

*[ENVIRONMENT]*

Set environment to check versions against. Defaults to development.

```
$ npx dotenv-vault versions production
```

##### FLAGS

*-m, --dotenvMe*

Pass .env.me (DOTENV_ME) credential directly (rather than reading from .env.me file)

```
$ npx dotenv-vault versions dotenvMe=me_b1831e…
```

*-y, --yes*

Automatic yes to prompts. Assume yes to all prompts and run non-interactively.

```
$ npx dotenv-vault versions -y
```

If you want to pull a specific version you can do so. For example,

```
npx dotenv-vault pull development@v14
```

---

### `local build`

Build .env.vault from local only

Example:

```bash
$ npx dotenv-vault local build
```

This will encrypt the contents of your `.env` file and any `.env.ENVIRONMENT` files you have locally into your `.env.vault` file.

### `local decrypt`

Decrypt .env.vault from local only

Example:

```bash
$ npx dotenv-vault local decrypt dotenv://:key_1234@dotenv.local/vault/.env.vault?environment=development
```

##### ARGUMENTS

*[DOTENV_KEY]*

Set `DOTENV_KEY` to decrypt .env.vault. Development key will decrypt development, production will decrypt production, and so on.

```
$ npx dotenv-vault local decrypt dotenv://:key_1234@dotenv.local/vault/.env.vault?environment=development
```

### `local keys`

List .env.vault local decryption keys from .env.keys file

Example:

```bash
$ npx dotenv-vault local keys
local:    Listing .env.vault decryption keys from .env.keys... done
 environment DOTENV_KEY
 ─────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────
 develompent dotenv://:key_33ee..@dotenv.local/vault/.env.va…
 production  dotenv://:key_7038..@dotenv.local/vault/.env.va…
```

##### ARGUMENTS

*[ENVIRONMENT]*

Set `ENVIRONMENT` to output a single environment's DOTENV_KEY.

```
$ npx dotenv-vault local keys development…
local:    Listing .env.vault decryption keys from .env.keys... done
dotenv://:key_a682c..@dotenv.local/vault/.env.vault?environment=development
```

## ❓ FAQ

### Why is the `.env.vault` file not decrypting my environment variables successfully?

First, make sure you are using `dotenv@16.1.0` or greater. (If you are using a different language make sure you have installed one of its [libraries](#what-languages-does-this-work-with).)

Second, test decryption is working locally.

```bash
$ dotenv-vault decrypt dotenv://:key_1234..@dotenv.local/vault/.env.vault?environment=production
# outputs environment variables
```

Third, test decryption on boot is working locally.

```bash
$ DOTENV_KEY=dotenv://:key_1234..@dotenv.local/vault/.env.vault?environment=production npm start
# boots your app with production envs
```

### Should I commit my `.env.vault` file?

Yes. It is safe and recommended to do so. DO commit your `.env.vault` file to code. DO NOT commit your `.env` file. The `.env.vault` file contains ciphertext generated using AES-256. AES-256 is trusted by the US Government to transmit top-secret information and has a brute-force timescale of about a billion years.

### I accidentally leaked my `DOTENV_KEY`, what can I do? 

Does that attacker also have access to your `.env.vault` file?

* No: good, the attacker cannot do any damage. They need both the `DOTENV_KEY` and `.env.vault` file to access your secrets. This extra layer of security sets the `.env.vault` file apart as a superior solution to other SecretOps solutions.
* Yes: IMMEDIATELY start rotating your secrets at your third-party API providers. This scenario would be the same no matter what SecretOps solution you use.

After completing the above, rotate your `DOTENV_KEY` using the [rotatekey](#rotatekey) command, rebuild your `.env.vault` file, and redeploy.

### Is it safe to store my secrets with dotenv-vault?

It safer than scattering your secrets across multiple cloud providers. Those providers are focused on code deployment and server performance over secrets security.[1]

Dotenv Vault's singular focus is secrets security, and as a result we go to great lengths to make sure your secrets are safe. Afterall, we keep our secrets here too.[2]

* [[1] CircleCI Breach](https://techcrunch.com/2023/01/05/circleci-breach/)
* [[2] Security at Dotenv Vault](https://www.dotenv.org/security)

### What languages does this work with?

The `.env.vault` file and its encryption algorithm is language-agnostic so technically it works with any language. We've built convenience libraries for it in a handful of languages and are adding more quickly.

* [Go](https://github.com/dotenv-org/godotenvvault)
* [Kotlin](https://github.com/dotenv-org/dotenv-vault-kotlin)
* [NodeJS](https://github.com/motdotla/dotenv)
* [PHP](https://github.com/dotenv-org/phpdotenv-vault)
* [Python](https://github.com/dotenv-org/python-dotenv-vault)
* [Ruby](https://github.com/dotenv-org/dotenv-vault-ruby)

### How do I use 💻 Locally Managed dotenv-vault?

There are a series of **💻 Locally Managed** commands available to you. Locally managed never makes a remote API call. It is completely managed on your machine.

**🔐 Vault Managed** adds conveniences like backing up your .env file, secure sharing across your team, access permissions, and version history.

**💻 Locally Managed** is a good choice for someone who would prefer to handle this coordination themselves and does not want to trust Dotenv Vault with their secrets. 

<a href="https://www.youtube.com/watch?v=Ad7Wl8iC3Rs">
<div align="right">
<img src="https://img.youtube.com/vi/Ad7Wl8iC3Rs/hqdefault.jpg" alt="how to deploy with a .env.vault file video tutorial" align="right" width="330" />
<img src="https://simpleicons.vercel.app/youtube/ff0000" alt="youtube/@dotenvorg" align="right" width="24" />
</div>
</a>

```bash
$ dotenv-vault help local
```

Build your local only `.env.vault` file. This will look for your `.env` file, your `.env.production` file, your `.env.staging` file, etc and encrypt them to your `.env.vault` file.

```bash
$ npx dotenv-vault local build 
```

View your `.env.keys` file.

```bash
$ cat .env.keys
```

Use the values in your `.env.keys` file to set `DOTENV_KEY` on your server.

```bash
# heroku example
heroku config:set DOTENV_KEY=dotenv://:key_1234…@dotenv.org/vault/.env.vault?environment=production
```

That's it! Just be careful when manually sharing this `.env.keys` file across your team, as there are no access permission protections like you get with dotenv-vault's default service.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)

## Changelog

See [CHANGELOG.md](CHANGELOG.md)

## License

MIT
