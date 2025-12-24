# n8n Installation and Setup Guide

This guide provides step-by-step instructions on how to install n8n and import the workflows provided in this repository.

## 1. Installing n8n

You can run n8n in several ways. We recommend using **Docker** for the best self-hosted experience.

### Option A: Using Docker (Recommended)

1.  Ensure you have **Docker** installed on your machine.
2.  Run the following command to start n8n:

    ```bash
    docker run -it --rm \
      --name n8n \
      -p 5678:5678 \
      -v ~/.n8n:/home/node/.n8n \
      docker.n8n.io/n8nio/n8n
    ```

    *   `-p 5678:5678`: Exposes n8n on port 5678.
    *   `-v ~/.n8n:/home/node/.n8n`: Persists your data (workflows, credentials) to your home directory.

3.  Open your browser and navigate to `http://localhost:5678`.

### Option B: Using npm

If you have **Node.js** installed, you can install n8n globally:

1.  Install n8n:
    ```bash
    npm install n8n -g
    ```
2.  Start n8n:
    ```bash
    n8n
    ```
3.  Open your browser and navigate to the URL shown in the terminal (usually `http://localhost:5678`).

### Option C: n8n Cloud

If you prefer a managed service, you can sign up for [n8n Cloud](https://n8n.io/cloud/).

---

## 2. Importing Workflows

Once n8n is running, you can import the JSON files from this repository.

### Method 1: Import from File (Best for preservation)

1.  In the n8n dashboard, click the **"Add details"** menu (three dots or plus icon) in the top right corner of the workflow list or canvas.
2.  Select **"Import from File"**.
3.  Browse and select one of the `.json` files from this repository (e.g., `Bibliographic Search.json`).
4.  The workflow will load into the canvas. Click **Save** to store it.

### Method 2: Copy and Paste

1.  Open the `.json` file in a text editor.
2.  Select all text and copy it (`Ctrl+C` / `Cmd+C`).
3.  Go to your n8n dashboard and open a new blank workflow.
4.  Click anywhere on the canvas and paste (`Ctrl+V` / `Cmd+V`).
5.  The nodes should appear. Click **Save**.

---

## 3. Post-Import Configuration

After importing, you must configure the workflows to work with your environment.

### A. Update Credentials
Most workflows require API keys. You will see nodes with warnings if credentials are missing.
1.  Click on nodes like **OpenAI**, **Anthropic**, or **PostgreSQL**.
2.  Select "Create New Credential" or choose an existing one.
3.  Enter your API keys (e.g., `sk-...` for OpenAI).

### B. Configure Paths and Placeholders
Look for the **"Workflow Configuration"** node (usually a `Set` node) at the beginning of the workflow. Update the values:
*   **API URLs**: If endpoints are required.
*   **File Paths**: For workflows like `File System Stuff`, ensure the `inputDirectory` and `outputDirectory` exist on the machine running n8n.
*   **Database**: Ensure your PostgreSQL connection string is correct.

You are now ready to run the automations! 🚀
