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

## SonarQube Analysis

This repository includes a basic SonarQube configuration and a CI workflow to run scans.

- **Config:** `sonar-project.properties` at repository root contains project settings.
- **CI:** A GitHub Actions workflow is provided at [.github/workflows/sonarqube.yml](.github/workflows/sonarqube.yml#L1) which runs the SonarScanner Docker image.
- **Secrets required for CI:**
	- `SONAR_HOST_URL` - your SonarQube server URL (e.g. `https://sonar.yourcompany.com` or `https://sonarcloud.io`)
	- `SONAR_TOKEN` - a token generated in SonarQube (user or project token)

To run locally:

```powershell
$env:SONAR_HOST_URL = 'https://sonar.example.com'
$env:SONAR_TOKEN = 'YOUR_TOKEN'
sonar-scanner
```

Or with Docker (no local scanner install):

```bash
docker run --rm -e SONAR_HOST_URL="$SONAR_HOST_URL" -e SONAR_LOGIN="$SONAR_TOKEN" -v "$(pwd):/usr/src" sonarsource/sonar-scanner-cli
```

After the workflow completes, view scan results in your SonarQube instance under the project key `Fossa-Accelerator`.
