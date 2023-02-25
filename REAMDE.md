# go-slsa-example

Example SLSA GO Release Workflow

# Verify Artifact

```shell
$ wget https://github.com/mrtc0-sandbox/go-slsa-example/releases/download/v0.0.4/hello-slsa-darwin-arm64
$ wget https://github.com/mrtc0-sandbox/go-slsa-example/releases/download/v0.0.4/hello-slsa-darwin-arm64.intoto.jsonl

$ slsa-verifier verify-artifact --provenance-path ./hello-slsa-darwin-arm64.intoto.jsonl --source-uri github.com/mrtc0-sandbox/go-slsa-example --source-tag v0.0.4 ./hello-slsa-darwin-arm64
Verified signature against tlog entry index 14131378 at URL: https://rekor.sigstore.dev/api/v1/log/entries/24296fb24b8ad77a5e3a6cc6327810a25ba64147739404b632dd2f61b1fa7cea3b2e542c1a2c6122
Verified build using builder https://github.com/slsa-framework/slsa-github-generator/.github/workflows/builder_go_slsa3.yml@refs/tags/v1.4.0 at commit 14275c7e0a3d7eb448ad01fd014d7e1cceac70da
PASSED: Verified SLSA provenance
```

# References

- https://github.com/slsa-framework/slsa-github-generator/blob/main/internal/builders/go/README.md#configuration-file
