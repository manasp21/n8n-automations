# Contributing to n8n Automations

Thank you for your interest in contributing to this project! We welcome improvements, bug fixes, and new workflows.

## How to Contribute

1.  **Fork the Repository**: Create a fork of this repository to your own GitHub account.
2.  **Clone the Repository**: Clone your fork to your local machine.
    ```bash
    git clone https://github.com/yourusername/n8n-automations.git
    ```
3.  **Create a Branch**: Create a new branch for your feature or fix.
    ```bash
    git checkout -b feature/my-new-workflow
    ```
4.  **Make Changes**: Add your new n8n workflow `.json` file or modify existing ones.
    - If adding a new workflow, please export it from n8n with **all sensitive credentials removed**.
    - Ensure your workflow is named clearly.
5.  **Update Documentation**:
    - If you added a new workflow, please update `README.md` to include a description of what it does and any prerequisites.
6.  **Commit and Push**:
    ```bash
    git add .
    git commit -m "Add new workflow for [Purpose]"
    git push origin feature/my-new-workflow
    ```
7.  **Submit a Pull Request**: Open a Pull Request (PR) from your branch to the `main` branch of this repository. Please provide a clear description of your changes.

## Guidelines

- **Sensitive Data**: Never commit API keys, passwords, or personal tokens. Use n8n's credential system or placeholder values (e.g., `<API_KEY>`) in your exported JSON.
- **Testing**: Please test your workflow to ensure it executes correctly before submitting.
- **Format**: Keep workflow JSON files formatted for readability if possible.

## License

By contributing, you agree that your contributions will be licensed under the MIT License of this project.
