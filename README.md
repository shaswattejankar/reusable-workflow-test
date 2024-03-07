## Reusable Workflow for React App

A repo that hosts a reusable file named build.yml in .github/workflows for building with npm and syncing the build file to a s3 bucket provided 

with 'secrets' to the reusable workflow file FROM the caller workflow. The secrets are stored in the caller workflow environment.

This reusable wrokflow can be used in the following manner:
```
# When a reusable workflow is referenced under a job_name do not use STEPS
job_name:
    uses: shaswattejankar/reusable-workflow-test/.github/workflows/build.yml@main
    secrets:
        aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
        aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        aws-s3-bucket: ${{ secrets.AWS_S3_BUCKET }}
        aws-region: ${{ secrets.AWS_REGION }}
```
