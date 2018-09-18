## Running FireWorks automatically

Start the Rocket Launcher so that it looks for new FireWorks every 10 seconds:

```shell
rlaunch --config_dir ./lpad_config --launchpad_file ./lpad_config/launchpad.yaml rapidfire --nlaunches infinite --sleep 10
```

The Rocket Launcher will run them automatically and create a new directory for each job added into the LaunchPad

## Rerunning a Firework or Workflow


## Rerunning a Firework or Workflow

You may want to rerun a Firework or Workflow when your computing resource may have crashed or been configured 
incorrectly during the first run, leading to your first launch being FIZZLED.

- Rerun specific fws

```shell
lpad rerun_fws --launchpad_file ./lpad_config/launchpad.yaml [-i FW_IDS] [-n NAME] [-s STATE] [-q QUERY]
```

launchpad = LaunchPad()


- Reset the LaunchPad (MongoDB)

```shell
lpad --config_dir ./lpad_config --launchpad_file ./lpad_config/launchpad.yaml reset
```

- Rerun a fireworl at task level, starting on the last task that caused the error

```shell
lpad rerun_fws --launchpad_file ./lpad_config/launchpad.yaml -s FIZZLED  --task-level
```

- Rerun all the FIZZLED fws

```shell
lpad rerun_fws --launchpad_file ./lpad_config/launchpad.yaml -s FIZZLED
```