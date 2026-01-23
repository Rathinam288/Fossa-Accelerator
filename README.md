"# Fossa-Accelerator" 
"# Fossa-Accelerator" 

## FOSSA Integration

- **CI:** A GitHub Actions workflow is included at [.github/workflows/fossa.yml](.github/workflows/fossa.yml#L1) that runs FOSSA on `push` and `pull_request`. Set the repository secret `FOSSA_API_KEY` to enable the scan.
- **Config:** A root `.fossa.yml` is present which enables `fossa analyze` for this project.
- **Run locally:** Install the FOSSA CLI (see FOSSA docs) and run:

```bash
fossa analyze
fossa test
```

If you'd like, I can attempt a local `fossa analyze` here — provide the API key or run it locally and share the output.
