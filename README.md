# `rearm-add-release`

## About
This action, uses the Rearm CLI, [`rearm`](https://github.com/relizaio/rearm), to submit the release metadata.
This action should always be used after the [`rearm-get-version`](https://github.com/relizaio/rearm-get-version) action.

## Usage

Submit Release metadata:

```yaml
steps:
- uses: relizaio/rearm-add-release@1.2
  with:
    rearm_api_id: <api-id-obtained-from-rearmhub>
    rearm_api_key: <api-key-obtained-from-rearmhub>
    image_full_name: <registry/owner/image>
    image_digest: <api-key-obtained-from-rearmhub>
    rearm_full_version: <version obtained on get-version step>
    rearm_build_start: <build start time recorded on get-version step>
    rearm_build_status: <complete|rejected>
```

## Inputs
The actions supports the following inputs:

- `rearm_api_id`: The project API ID obtained from Rearm.
- `rearm_api_key`: The project API Key obtained from Rearm.
- `image_full_name`: Full name of the Docker image with registry prefix
- `image_name`: Name of the image
- `image_digest`: SHA 256 digest of the image artifact
- `rearm_full_version`: Version obtained from Rearm for this release
- `rearm_build_start`: Build start time
- `rearm_build_status`: Build status - `complete` - if build succeded,  `rejected` - if build failed
- `artifact_type`: Type of artifact created by this release [Docker, File] (Optional)
- `commit_list`: List of commits (Optional)
- `enable_sbom`: Enables SBOM generation using cdxgen (Optional)
- `registry_username`: Username for the image registry. (Optional - needed for sbom generation)
- `registry_password`: Password for the image registry. (Optional - needed for sbom generation)
- `registry_host`: Image registry host. (Optional - needed for sbom generation)
- `path`: Path to the relative to root of the repo (default is '.').
 (Optional - needed for sbom generation)
