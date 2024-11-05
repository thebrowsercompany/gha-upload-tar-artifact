# `@thebrowsercompany/gha-upload-tar-artifact`

Tar and upload [Action Artifacts](https://docs.github.com/en/actions/using-workflows/storing-workflow-data-as-artifacts) from your Workflow Runs. Internally powered by GitHub's [@actions/upload-artifact](https://github.com/actions/upload-artifact) action. This action tars the provided path before using [@actions/upload-artifact](https://github.com/actions/upload-artifact) to upload the tar file, preserving permissions on non-Windows platforms.

See also [gha-download-tar-artifact](https://github.com/thebrowsercompany/gha-download-tar-artifact). For further documentation, refer to the [@actions/upload-artifact](https://github.com/actions/upload-artifact) documentation.

- [`@thebrowsercompany/gha-upload-tar-artifact`](#thebrowsercompanygha-upload-tar-artifact)
  - [Usage](#usage)
    - [Inputs](#inputs)
    - [Outputs](#outputs)

## Usage

### Inputs

```yaml
- uses: thebrowsercompany/gha-upload-tar-artifact@main
  with:
    # Name of the artifact to upload.
    name:

    # A file or directory that describes what to upload.
    # Required.
    path:

    # Duration after which artifact will expire in days. 0 means using default retention.
    # Minimum 1 day.
    # Maximum 90 days unless changed from the repository settings page.
    # Optional. Defaults to repository settings.
    retention-days:
```

### Outputs

| Name | Description | Example |
| - | - | - |
| `artifact-id` | GitHub ID of an Artifact, can be used by the REST API | `1234` |
| `artifact-url` | URL to download an Artifact. Can be used in many scenarios such as linking to artifacts in issues or pull requests. Users must be logged-in in order for this URL to work. This URL is valid as long as the artifact has not expired or the artifact, run or repository have not been deleted | `https://github.com/example-org/example-repo/actions/runs/1/artifacts/1234` |
