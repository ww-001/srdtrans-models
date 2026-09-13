# srdtrans-models

Mirror of [SRDTrans](https://github.com/cabooster/SRDTrans) pre-trained model
weights, fetched from Zenodo via GitHub Actions to bypass network restrictions
in mainland China.

## What's in here

The repo itself is empty — model weights are too large to commit. Trigger the
`fetch-models` workflow to populate a downloadable artifact:

- **calcium imaging** (cad_03hz, cad_30hz) — from Zenodo record [7818030](https://doi.org/10.5281/zenodo.7818030)
- **SMLM** — from Zenodo record [8332544](https://zenodo.org/record/8332544)

## Usage

1. Go to the **Actions** tab → select **Fetch SRDTrans models from Zenodo**
2. Click **Run workflow**
3. After the run completes, download the `srdtrans-models` artifact from the run page
4. Extract and copy the `.pth` files into `D:\srd_denoiser\models\` (or wherever your denoiser expects them)

## How it works

GitHub Actions runners have unrestricted internet and don't get blocked by
CERN-side firewall rules that affect Cloudflare IPs from China. The workflow
queries the Zenodo API, downloads each `.pth` file, and uploads them as a
single artifact.

## Related

- Desktop denoiser GUI: `D:\srd_denoiser\` (separate repo / local project)
- SRDTrans paper: Li et al., *Nature Computational Science* (2023), https://doi.org/10.1038/s43588-023-00568-2