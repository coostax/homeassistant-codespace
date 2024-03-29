# Homeassistant AddOns Codespace

Environment for developing home assistant add-ons using devcontainer, produced from (Home Assistant core repository)[https://github.com/home-assistant/core]

## Local add-on testing

The fastest and recommended way to develop add-ons is using a local Visual Studio Code dev environment. The Official Add-ons repository includes a dev container setup for VS Code which will run Supervisor and Home Assistant, with all of the add-ons mapped as Local Add-ons inside, making it simple for add-on developers on Windows, Mac and Linux desktop OS-es.

* Follow the instructions to download and install the Remote Containers VS Code extension.
* Copy the .devcontainer and .vscode folder from Official Add-ons repository into the root of your add-ons folders.
* Open the root folder inside VS Code, and when prompted re-open the window inside the container (or, from the Command Palette, select 'Rebuild and Reopen in Container').
* When VS Code has opened your folder in the container (which can take some time for the first run) you'll need to run the task (Terminal -> Run Task) 'Start Home Assistant', which will bootstrap Supervisor and Home Assistant.
* You'll then be able to access the normal onboarding process via the Home Assistant instance at http://localhost:7123/.
* The add-on(s) found in your root folder will automatically be found in the Local Add-ons repository.

## Local build with Standalone Docker

On the add-on folder where dockerfile is run the following:

´´´
docker build \
  --build-arg BUILD_FROM="ghcr.io/hassio-addons/debian-base/amd64:stable" \
  -t local/my-test-addon \
  .
´´´

## Local run

Does not seem to work with firefly..

´´´
docker run \
  --rm \
  -v /tmp/my_test_data:/data \
  -p PORT_STUFF_IF_NEEDED \
  local/my-test-addon
´´´

### Submodules

Add-ons exist as submodules, to switch a submodule to a development branch use the following commands:
```
git submodule update --init --recursive --remote
cd submodule_name
git checkout new_branch_name
```

## Usefull links

- https://github.com/home-assistant/addons-example - example add-on
- https://github.com/home-assistant/docker-base - home assistant base images