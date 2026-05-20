# AGENTS.md

## Workspace Purpose

This workspace is a notebook-first project for learning and iterating on continue pretraining and SFT for Qwen2.5-0.5B with medical data. The main working surface is `CPT.ipynb`.

## How to Work Here

- Prefer small, local changes in `CPT.ipynb` over broad refactors.
- Keep changes aligned with the current training pipeline: data loading, text extraction, tokenization, packing, training arguments, Trainer, saving, and generation checks.
- Treat `qwen-medical-pretrained/` and `wandb/` as generated artifacts unless the user explicitly asks to inspect or clean them.
- Do not overwrite checkpoints, optimizer state, or run logs unless that is the explicit task.
- When you need project context, inspect the notebook first instead of inventing conventions.

## Teaching Style For This Workspace

- Assume the user is learning LLM training in Vietnamese and prefers `tôi` / `bạn` form.
- Explain one concept at a time and connect it to the current notebook step.
- When asked to explain code, go line by line and keep the explanation concrete.
- Ask the user to run code and paste the output before moving to the next conceptual step when validation is needed.
- Use ASCII diagrams or short examples when they clarify tokenization, packing, masking, or training flow.

## Editing Preferences

- Preserve the existing notebook flow and naming conventions when adding cells or helper code.
- Favor reproducible settings already in use in the notebook, such as fixed seeds, causal LM data collators, and memory-conscious training choices.
- Keep new helper code minimal and easy to remove if it is only for experimentation.

## Validation

- Prefer cheap checks that validate the touched notebook slice, such as running the changed cell or verifying shapes, token counts, or a short generation sample.
- If training behavior changes, confirm the loss or training logs before expanding the change.
