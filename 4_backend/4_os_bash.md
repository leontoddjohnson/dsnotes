# Bash for Unix

## Running background process

In many cases, you'll want a script to run on your local computer "in the background" so that when your computer goes to sleep, or if you close a terminal, the script is still running.

**Run program**

```bash
nohup python <command> &
```

Don't forget the `&` at the end. This directs the process to be run in the background. The `nohup` directs output to a *nohup.out* file in the same (working) directory.

**Check Running Processes**

```bash
ps ax
ps ax | grep <script_name> 
```

The former will list the running processes, and the latter will list running processes with `<script_name>` in its name.

**Kill a Process**

If you're done with the script, run

```bash
kill <process_id>
```

To kill the process with `<process_id>` in the first column from the `ps` command, above.








