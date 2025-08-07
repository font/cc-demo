# CoCo Setup on Azure
## Azure CLI Installation on Fedora 41

Install using script for any Linux from instructions here:
https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?view=azure-cli-latest&pivots=script

However, it fails with an error caused by not using the correct version of
python as indicated in the
[requirements](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?view=azure-cli-latest&pivots=script#before-you-begin).

To fix:

```bash
sudo dnf install python3.10
python3.10 -m venv azure-cli-env
source azure-cli-env/bin/activate
# Verifies download using embedded sha256sum digest
curl -L https://aka.ms/InstallAzureCli | bash
deactivate
rm -rf azure-cli-env
```
