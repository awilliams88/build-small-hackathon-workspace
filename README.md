# Avenium Build Small Hackathon Workspace

This repository coordinates Avenium's Build Small Hackathon submissions. The goal is to maximize our chances in the cash prize pools by shipping public, polished Gradio Spaces targeting sponsor tracks, special categories, and merit badges.

## 1. Project Slate & Status

| Project | Trail | Target Sponsor | GitHub | Hugging Face Space | Status |
| --- | --- | --- | --- | --- | --- |
| **InnerSpace** | Backyard AI | OpenBMB, OpenAI | [innerspace](https://github.com/awilliams88/innerspace) | [innerspace Space](https://huggingface.co/spaces/build-small-hackathon/innerspace) | **Completed & Pushed** |
| **Pocket Tutor** | Backyard AI | OpenBMB | Pending | Pending | Planned |
| **Flux Costume Booth** | Thousand Token Wood | Black Forest Labs, Modal | Pending | Pending | Planned |
| **Tiny Quest Radio** | Thousand Token Wood | Cohere | Pending | Pending | Planned |
| **Roast My Repo** | Backyard AI | JetBrains, OpenAI | Pending | Pending | Planned |
| **Modal-Tuner** | Backyard / Developer | Modal, OpenBMB, Cohere | Pending | Pending | Planned |

---

## 2. Repository Structure

- [projects/neighbordocs/](projects/neighbordocs/) - Git submodule pointing to the `innerspace` project repository.
- [PROJECTS.md](PROJECTS.md) - Consolidated implementation plans and conceptual slate for all projects.
- [MODELS.md](MODELS.md) - Target sponsor models (OpenBMB, Black Forest Labs, JetBrains, Cohere) and Modal fine-tuning/quantization guides.
- [AWARDS.md](AWARDS.md) - Cash prize distributions, sponsor tracks, and merit badge stacking guidelines.
- [ARCHITECTURE.md](ARCHITECTURE.md) - Shared coding standards, separation of concerns, and quality rules.

---

## 3. Submission Checklist

Every project repository must include:
* A Hugging Face Space-compatible `README.md` with frontmatter.
* A public GitHub repository link in the Space README.
* A model table detailing model names, parameter counts, and sponsor alignment.
* Standard flat structure: `app.py`, `config.py`, `core.py`, `ui.py`, `requirements.txt`, and `run.sh`.
* A verification script (`./run.sh verify`) that runs Ruff formatting/linting, Pyright type checking, and compilation checks.

Every final submission must include:
* Public Hugging Face Space under the `build-small-hackathon` organization.
* A short demo video link and a social post link in the Space README.

---

## 4. Operating Rules
* **Git Commit Signatures**: All commits must be authored as `Codex <codex@openai.com>` for OpenAI track evaluation.
* **Remote Synchronization**: Push identical Git branches to both GitHub (`origin`) and Hugging Face (`hf`) to maintain a single, synchronized commit history. Do not use `hf upload` for code updates.
* **Separation of Concerns**: UI logic resides in `ui.py` with custom dark styling, and core inference/logic resides in `core.py` (with no Gradio imports, and including any ZeroGPU decorators).
* **Model Constraints**: No model in any submission may exceed the **32B total-parameter cap**.


---

## 5. Recommended Git Remotes & Troubleshooting

For each new project submodule, configure the remotes to push to both GitHub and Hugging Face:

```bash
git remote add origin https://github.com/awilliams88/<project>.git
git remote add hf https://huggingface.co/spaces/hackathon/<project>
git push origin main
git push hf main
```

If histories diverge between GitHub and Hugging Face, force-push the known-good project branch to the HF remote after verifying the files are correct:

```bash
git push --force-with-lease hf main
```

