# Run Streamlit on Codespaces

Fork this repo, add your Streamlit app to it, and run it on GitHub Codespaces. :balloon:

## How it works

- `.devcontainer/devcontainer.json` creates a container with Python 3.7 and the latest version of Streamlit.
- It uses `forwardPorts` to make port `8501` inside the container available locally.
- Additionally, it sets the following configuration options in `.streamlit/config.toml` so that the app can be run on Codespaces without the addition of command line arguments:

    ```toml
    [server]
    enableCORS = false
    enableXsrfProtection = false
    ```

## Example usage

Fork this repo, open it on GitHub Codespaces, and run the following command to view the Hello app:

```bash
streamlit hello
```

![st-codespaces](https://user-images.githubusercontent.com/20672874/173758145-674a171a-60de-4850-a30f-ab8b921ffd43.gif)

If it weren't for the `.streamlit/config.toml` file, you would have had to run the following command:

```bash
streamlit hello --server.enableCORS false --server.enableXsrfProtection false
```
