# Local add-on testing

The fastest and recommended way to develop add-ons is using a local Visual Studio Code dev environment. The Official Add-ons repository includes a dev container setup for VS Code which will run Supervisor and Home Assistant, with all of the add-ons mapped as Local Add-ons inside, making it simple for add-on developers on Windows, Mac and Linux desktop OS-es.

* Follow the instructions to download and install the Remote Containers VS Code extension.
* Copy the .devcontainer and .vscode folder from Official Add-ons repository into the root of your add-ons folders.
* Open the root folder inside VS Code, and when prompted re-open the window inside the container (or, from the Command Palette, select 'Rebuild and Reopen in Container').
* When VS Code has opened your folder in the container (which can take some time for the first run) you'll need to run the task (Terminal -> Run Task) 'Start Home Assistant', which will bootstrap Supervisor and Home Assistant.
* You'll then be able to access the normal onboarding process via the Home Assistant instance at http://localhost:7123/.
* The add-on(s) found in your root folder will automatically be found in the Local Add-ons repository.

# Usefull links

- https://github.com/home-assistant/addons-example - example add-on
- https://github.com/home-assistant/docker-base - home assistant base images