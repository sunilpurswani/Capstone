
# Capstone — Modular Multi-Agent Framework

A research-oriented multi-agent framework and examples focused on modular embeddings, discovery, and domain-specific agents. This repository contains a lightweight agent runtime, example domain agents, embedding adapters, telemetry hooks, and example scripts to run and experiment locally.

## Highlights

- Modular adapter architecture for embedding providers and agent discovery.
- Example domain agents (financial, healthcare, web development, reporting).
- Tools and scripts for local deployment, testing, and agent evaluation.
- Telemetry and metrics collection components (MongoDB integrations present).

## Quick start

1. Create a Python virtual environment and activate it.

```bash
# macOS / zsh
python3 -m venv .venv
source .venv/bin/activate
```

2. Install project dependencies.

```bash
pip install -r streamlined-adapter/requirements.txt
```

3. Run the demo script (simple entry point):

```bash
python demo.py
```

4. If you want to run the enhanced local agent tests or examples, try:

```bash
python streamlined-adapter/test_complete_system_local.py
python streamlined-adapter/test_agent.py
```

Note: some example scripts expect local services (e.g., MongoDB) or API keys for embedding providers. Check the related modules under `streamlined-adapter/nanda_core` and `streamlined-adapter/embeddings` for specific config hints.

## Project layout (key files and folders)

- `demo.py` — Lightweight demo driver for quick experiments.
- `deploy-*.sh` — Helper scripts for deployment targets (AWS / Linode examples).
- `streamlined-adapter/` — Main Python package containing adapters, agents, examples, and tests:
	- `examples/` — Example agent configs and domain agents.
	- `nanda_core/` — Core runtime: adapters, agent bridge, discovery, telemetry, embeddings.
	- `embeddings/` — Embedding provider implementations and managers.
	- `scripts/` — Additional helper scripts and example agent configs.
	- `test_*.py` — Unit/integration tests and examples used for validation.

## Configuration

- Many components read configuration from JSON files under `streamlined-adapter/` and the `scripts/agent_configs` folder. Example config files include:
	- `streamlined-adapter/embedding_config.json`
	- `streamlined-adapter/streamlined-adapter/embedding_config.json` (if present)
	- `streamlined-adapter/scripts/*.json`

- If you use MongoDB for telemetry or agent facts, set the connection URL in the modules that reference `mongodb` or set environment variables expected by those modules.

## Running tests

Run tests from the project root using `pytest`. Example:

```bash
pip install pytest
pytest -q
```

Some tests under `streamlined-adapter/` exercise integration points and may require external services or API keys. Use selective test invocation to run unit-only tests.

## Development notes

- Code style and minimal refactoring: keep changes local to the package under `streamlined-adapter/`.
- When adding new embedding providers, implement the base interface found in `streamlined-adapter/nanda_core/embeddings/base_embedder.py`.
- Discovery and ranking logic lives in `streamlined-adapter/nanda_core/discovery`.

## Examples and demo scripts

- `demo.py` — Good first stop for seeing a minimal flow.
- `streamlined-adapter/deploy_enhanced_local.py` — Local enhanced agent runner.
- `streamlined-adapter/examples/` — Browse these for agent templates and usage patterns.

## Contributing

If you'd like to contribute:

- Fork the repo and create a feature branch.
- Keep changes small and focused; add tests for new features.
- Open a PR and provide a short description and any required setup steps.

## License & contact

This repository does not include an explicit license file. If you intend to open-source it, add a `LICENSE` file (for example, MIT or Apache-2.0).

For questions or help, open an issue or contact the repository owner.

---

If you want, I can also:

- Add a short `requirements.txt` at the repo root that aggregates the ones in `streamlined-adapter/`.
- Generate small runnable examples with environment variable placeholders and a `.env.example`.
- Update or add a `LICENSE` file.
Tell me which of the above you'd like next.

