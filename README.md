# Run Streamlit on Codespaces

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/snehankekre/st-codespaces?quickstart=1)

Fork this repo, add your Streamlit app to it, and run it on GitHub Codespaces. :balloon:

## How it works

- `.devcontainer/devcontainer.json` creates a container with Python 3.10, installs your app dependencies from `requirements.txt`, and launches `streamlit hello`. 
    -  Edit the `postAttachCommand` to launch your app instead of Streamlit Hello. E.g. if your script is `app.py`:
        ```json
        "postAttachCommand": "streamlit run app.py",
        ```
- It uses `forwardPorts` to make port `8501` inside the container available locally.
- Additionally, it sets the following configuration options in `.streamlit/config.toml` so that the app can be run on Codespaces without the addition of command line arguments:

    ```toml
    [server]
    enableCORS = false
    enableXsrfProtection = false
    ```

## Example usage

Fork this repo, open it on GitHub Codespaces, wait for the container to load, and click the "Open in browser" button in the bottom right corner when it appears to open the Hello app:

![st-codespaces](https://github.com/snehankekre/st-codespaces/assets/20672874/9e31e47f-1fce-4213-a973-e7ed1259a480)


If it weren't for the `.streamlit/config.toml` file, you would have had to run the following command:

```bash
streamlit hello --server.enableCORS false --server.enableXsrfProtection false
```
