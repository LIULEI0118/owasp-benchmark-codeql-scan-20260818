# OWASP Benchmark CodeQL scan

This repository is a temporary, source-only scan mirror for the intentionally
vulnerable OWASP Benchmark for Java 1.2.

## Source package

- Original archive: `owasp-benchmark.zip`
- SHA-256: `95866d1cdc6b7a8f367f6acd3c8f16396e41f4adabc0925ab59d3490dcb094af`
- Size: 17,585,420 bytes
- Stored as 34 numbered parts under `source/`

The workflow reassembles the archive and verifies the SHA-256 before any build
or analysis step. It does not start the benchmark web application, LDAP server,
database, Tomcat, Cargo, Docker, or any deployment profile.

## CodeQL configuration

- Language: Java/Kotlin (`java-kotlin`)
- Query suite: `security-extended`
- Build mode: manual Maven build
- JDK: Temurin 17, compiling the project for Java 8 as configured by the POM
- Build command: `mvn -B -DskipTests -Dspotless.apply.skip=true -Dspotless.check.skip=true clean package`

The workflow uploads results to GitHub Code Scanning and also preserves the
generated SARIF directory as the `codeql-sarif` Actions artifact for complete
offline review.

> **Warning**
> This project intentionally contains vulnerable code for security-tool
> benchmarking. Do not deploy or expose it as an application.
