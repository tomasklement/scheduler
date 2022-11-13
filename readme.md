# Scheduler

Run scripts periodically on system which is irregularily powered down

## Synopsis
```bash
./scheduler [ POSIX options ] -s <script>
```
## Description
Example:
```bash
./scheduler -i 12345 -s /home/foo/script.sh
```
When this example is added to CRON, it executes given script in the first run. For other consecutive runs it checks if time of 12345 seconds elapsed and executes the script after that time period.

Scheduler must be able to write to its directory to save last run time and lock file.

## Options
**-s**
<p style="margin-left: 2em;">Path to script to be executed. User must have execute rights to that file</p>

**-i**
<p style="margin-left: 2em;">Minimal interval between script executions in seconds</p>

**-u**
<p style="margin-left: 2em;">Removes lock file. Useful for cases when something went wrong and lock file was not deleted after execution of script.</p>

**-l**
<p style="margin-left: 2em;">Prints formatted last script execution time.</p>

**-n**
<p style="margin-left: 2em;">Prints formatted next (nearest) script execution time.</p>

## Installation
You need to have installed GIT before running this command. To install run:
```bash
git clone git@github.com:tomasklement/scheduler.git && git -C scheduler submodule update --init --recursive
```
This will create directory "scheduler" and clone the latest version with its submodules from github.

## Upgrade
To upgrade to the latest version simply run:
```bash
./upgrade
```
This will pull the latest version with its submodules from github.