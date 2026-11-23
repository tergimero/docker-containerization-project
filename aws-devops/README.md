
# AWS DevOps CI Pipeline

## Project Overview
This project demonstrates a cloud-native Continuous Integration (CI) pipeline using AWS CodeCommit, CodeBuild, CodePipeline, IAM, and Amazon S3.

## AWS Services Used
- AWS CodeCommit — Stores application source code.
- AWS CodeBuild — Builds and tests the application.
- AWS CodePipeline — Automates the CI workflow.
- AWS IAM — Manages service roles and permissions.
- Amazon S3 — Stores pipeline artifacts.

## Project Configuration
- AWS Region: eu-north-1 (Stockholm)
- Repository: PythonDevOpsRepo
- Build Project: PythonDevOpsBuild
- Pipeline: PythonDevOpsPipeline
- Source Stage: AWS CodeCommit
- Build Stage: AWS CodeBuild

## IAM Roles
### CodeBuild Role
Role: PythonDevOpsCodeBuildRole

Policies:
- AWSCodeBuildDeveloperAccess
- CodeBuildBasePolicy-PythonDevOpsCodeBuildRole-eu-north-1
- PythonDevOpsBuildExecutionPolicy

### CodePipeline Role
Role: PythonDevOpsCodePipelineRole

Policies:
- AWSCodePipelineServiceRole-eu-north-1-PythonDevOpsPipeline
- CodePipeline-CodeBuild-eu-north-1-PythonDevOpsPipeline
- CodePipeline-CodeCommit-eu-north-1-PythonDevOpsPipeline

## Environment Variables
No environment variables are documented in the available project evidence.

## CI Pipeline Workflow
1. Application code is stored in AWS CodeCommit.
2. AWS CodePipeline retrieves the source code.
3. AWS CodeBuild executes the build process.
4. The pipeline reports successful or failed execution.
5. Pipeline artifacts are stored in Amazon S3.

## Testing and Results
- Source Stage: Succeeded
- Build Stage: Succeeded
- CodeBuild: Four successful builds observed
- S3: Build artifacts confirmed

## Evidence
Screenshots are stored in the screenshots directory.

## Conclusion
The AWS CI pipeline successfully integrates CodeCommit, CodeBuild, CodePipeline, IAM, and S3 to automate the source and build workflow.

