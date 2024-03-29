# Conversation Analytics Github Repository

## Repository Best Practices
- **No merging into main without Preface**
  
## New Code Workflow
1. Create a new branch off of `main`
2. Add your code
3. Open a pull request (PR) with notes
4. PR approval process:
   - Deployment tests, linting, etc.
   - If successful, merge PR and remove old branch

## Repository Auto Ruleset
- **Merging and branch management**
  - Remove old commits?
- **Security Checks**
- **Access Control**

## Deployment Strategies
- **Testing where possible**
- **Functions in Function App**
- **GitHub Actions**
  - Consistent format & logging
  - Code linting during deployment

## Generic Guidelines
- **Black and Formatting rules**
- **Set Coding Standards**
  - Typing, func strings, return types
- **User auth and usernames**
- **SQL Injection**
  - Parameterize queries!
- **CORS**
  - Backend currently accepts any IP
- **Implementation of Standard Logging Levels**
  - Info: Need to know when something happens (tracking)
  - Debug: Shouldn't be used in prod
  - Warning: A known exception and code is programmed to still continue
  - Error: Investigate immediately, something is broken. Working code should never log error
- **Exception Handling**
  - Try not to use generic exceptions, if we do, use trackbacks
- **Implementation of Standard Slack Alerts**
  - Alerts for errors
  - Alerts for major info (Deployments, etc.)

## Project Notes

### AnalyticsDataProcessing
- **Remove dev imports**
- **Add environment variables, remove hardcoded secrets**
- **FunctionApp Emulator** 
  - New repo - copy common code from ADP
- **Moving of current files to archive & renaming functions to CustomerId**
  - Move current to archive
  - Rename functions
  - Redeploy functions
  - Remove old blob receipts
  - Reprocessing functionality
  - Needs thinking on how to run with archive containers
  - Possible HTTP trigger in each existing function

### AnalyticsBackend
- **Remove unused routes**
- **User auth standardization**
- **Extra careful when no auth, how to handle CustomViz's**

### CustomViz's
- **TypeScript:** Reuse as much as possible
- **CSS:** Develop a library for components (master CSS file)
- **Alerting (Slack)**
- **Generic Visual Settings**

### AnalyticsTenantManager
- **Deployment processes need to include all config items**
  - CustomerDataInfo, etc.
- **If successful deployment (with data) then add Phrases stored proc into DB**
- **Deployment processes need to make a call to backend to process files**
- **What to do with empty deployments**
  - Empty deployment flag
