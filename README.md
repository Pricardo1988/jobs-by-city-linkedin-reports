# Jobs By City LinkedIn Reports

[![Jobs By City](https://github.com/GuillaumeFalourd/jobs-by-city-linkedin-reports/actions/workflows/1-jobs-by-city.yml/badge.svg)](https://github.com/GuillaumeFalourd/jobs-by-city-linkedin-reports/actions/workflows/1-jobs-by-city.yml)

[![Jobs By City (EMAIL)](https://github.com/GuillaumeFalourd/jobs-by-city-linkedin-reports/actions/workflows/2-jobs-by-city-sendgrid.yml/badge.svg)](https://github.com/GuillaumeFalourd/jobs-by-city-linkedin-reports/actions/workflows/2-jobs-by-city-sendgrid.yml)

![Sample](/docs/repo-title.png)

This reports contains an automation to get `jobs by city LinkedIn reports` using [Github Actions](https://github.com/features/actions) and [Ritchie CLI](https://ritchiecli.io).

## 📝  Description

This automation uses this [Ritchie CLI formula](https://github.com/GuillaumeFalourd/formulas-insights/tree/master/linkedin/search/jobs) to scrape public LinkedIn pages to find jobs by city and to generate a CSV report with all relevant jobs datas.

## 🕵️  Sample of generated reports

Reports will look like this one:

![Sample](/docs/report-sample.png)

## 🧐  Expected Behaviour

If you run the workflow too frequently, you might get a `Http Status 429` error for too many requests attempts.

*Suggestion: Wait for 1h when this occur to try again.*

## ♻️  Want to automate your login as well?

**Create a new repository** (you can clone or fork this one)

```bash
git clone https://github.com/GuillaumeFalourd/linkedin-jobs-by-city-reports-automation.git
```

Then, you have 2 options:

  ### 1️⃣  Without email notification

- On the file [(1-jobs-by-city.yml)]([todo](https://github.com/GuillaumeFalourd/jobs-by-city-linkedin-reports/blob/main/.github/workflows/1-jobs-by-city.yml)), add 2 environment variables:
  - `RIT_JOB_TITLE` with the JOB TITLE you're looking for.
  - `RIT_JOB_CITY` with the JOB CITY you're interested in.

In that case, you'll only see new reports generated on the repository `/reports` directory.

  ### 2️⃣  With email notification

You'll need to use **[SendGrid](https://sendgrid.com/)** (it's **FREE** until 100 emails sent / day).

- As for the option 1: on the file [(2-jobs-by-city-sengdrid.yml)]([todo](https://github.com/GuillaumeFalourd/jobs-by-city-linkedin-reports/blob/main/.github/workflows/2-jobs-by-city-sendgrid.yml)), add 2 environment variables:
  - `RIT_JOB_TITLE` with the JOB TITLE you're looking for.
  - `RIT_JOB_CITY` with the JOB CITY you're interested in.

- Add 3 secrets on the new repository ([here is a reference](https://docs.github.com/en/actions/reference/encrypted-secrets)):
  - a secret `RIT_EMAIL_RECEIVER`  with your stackoverflow account username.
  - a secret `RIT_SENDGRID_API_KEY` with your sendgrid API Key.
  - a secret `RIT_SENDGRID_EMAIL_SENDER` with yoru sendgrid email sender address.

In that case, you'll not only see new reports generated on the repository `/reports` directory, but you'll be notified by mail receiving a notification each time the workflow will be triggered (*note that the SENDGRIG free limit is 100 emails / day*)

*Note: [You can also use Ritchie CLI to add new secrets to your repository](https://github.com/GuillaumeFalourd/formulas-github/tree/master/github/add/secret)*

## 🔐  Secrets

![Secrets](/docs/repo-secrets.png)

## 🔁  Workflow Demo

![Demo](https://user-images.githubusercontent.com/22433243/114235444-9589b800-9956-11eb-8278-62f710db164f.png)

