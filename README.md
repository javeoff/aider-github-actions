# 🤖 GitHub Aider Action

This repository contains GitHub Actions workflows that automatically generate pull requests using [Aider](https://github.com/paul-gauthier/aider) in response to issues labeled with 'aider'.

## 🔄 How It Works

1. When an issue is labeled with 'aider' 🏷️, the workflow is triggered
2. 🌿 A new feature branch is created based on the issue title
3. 🤖 Aider processes the issue description as instructions and makes the requested changes
4. ✨ The changes are committed and a pull request can be created

## 🛠️ Setup

1. Configure one or more of the following API keys as repository secrets:
   - `OPENAI_API_KEY`
   - `ANTHROPIC_API_KEY`
   - `GEMINI_API_KEY`
   - `GROQ_API_KEY`
   - `COHERE_API_KEY`
   - `DEEPSEEK_API_KEY`
   - `OPENROUTER_API_KEY`

2. Create a GitHub Personal Access Token (PAT) with `repo` scope and add it as a repository secret named `GH_TOKEN`. This token is required for:
   - Creating branches
   - Committing changes
   - Creating pull requests
   - Other GitHub API operations

3. The workflow will be triggered when you add the `aider` label to any issue

## ⚙️ Configuration

The main workflow can be customized through the following inputs:

- `base-branch`: Base branch to create PR against (default: repository's default branch)
- `chat-timeout`: Timeout for chat in minutes (default: 10)
- `model`: AI model to use (default: gpt-4-1106-preview)

## 📝 Usage

1. Create an issue describing the changes you want to make
2. Add the `aider` label to the issue
3. The workflow will create a new branch and apply the requested changes
4. Review the changes and create a pull request if desired

## 📋 Example

Here's a sample issue that demonstrates how to use the GitHub Aider Action:

### Issue Title
"Update error handling in login.js"

### Issue Description
```
Please improve the error handling in login.js:
1. Add try/catch blocks around the database queries
2. Show user-friendly error messages
3. Add logging for debugging
```

When you add the `aider` label to this issue:
1. A new branch named `update-error-handling-in-login-js` will be created
2. Aider will process these instructions and make the requested changes
3. The changes will be committed to the branch
4. You can then review and create a PR with the changes

The more specific and clear your issue description is, the better results you'll get from Aider.

## 📦 Artifacts

The workflow saves the Aider chat history as an artifact that can be downloaded from the workflow run page.
