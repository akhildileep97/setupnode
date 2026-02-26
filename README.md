# Node CI Composite Action

A reusable GitHub Composite Action for standardizing Node.js CI pipelines.

This action:

* Sets up Node.js
* Installs dependencies
* Runs lint (optional)
* Runs tests (optional)
* Builds the project

Designed for teams that want consistent CI across multiple repositories.

---

## 🚀 Usage

```yaml
name: CI

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run Node CI Pipeline
        uses: akhil/node-ci-composite-action@v1
        with:
          node_version: "18"
```

---

## 📥 Inputs

| Name          | Required | Default       | Description            |
| ------------- | -------- | ------------- | ---------------------- |
| node_version  | ✅ Yes    | -             | Node.js version to use |
| run_lint      | ❌ No     | true          | Run `npm run lint`     |
| run_test      | ❌ No     | true          | Run `npm test`         |
| build_command | ❌ No     | npm run build | Custom build command   |

---

## 🛠 Example With All Options

```yaml
- uses: akhil/node-ci-composite-action@v1
  with:
    node_version: "20"
    run_lint: "true"
    run_test: "true"
    build_command: "npm run build"
```

---

## 📌 Requirements

Your project must include:

* package.json
* npm scripts for lint/test/build (if enabled)

---

## 🔖 Versioning

This action follows semantic versioning.

Use:

```yaml
@v1
```

to always receive backward-compatible updates.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

---

## 📄 License

MIT License
