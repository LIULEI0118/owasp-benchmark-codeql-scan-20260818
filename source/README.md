# Reassembling the source archive

From the repository root on Linux or macOS:

```sh
cat source/owasp-benchmark.zip.part-* > /tmp/owasp-benchmark.zip
echo "95866d1cdc6b7a8f367f6acd3c8f16396e41f4adabc0925ab59d3490dcb094af  /tmp/owasp-benchmark.zip" | shasum -a 256 -c
unzip -q /tmp/owasp-benchmark.zip -d /tmp/owasp-benchmark-source
```

The archive contains one top-level directory named `owasp-benchmark/`.
