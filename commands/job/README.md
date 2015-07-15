
### Examples

Export the server url and api-token so you dont have to set them as command options:

	export SERVER_URL=http://localhost:4440
	export API_TOKEN=xxxxxxxxxxxxxxxxxxx

#### Run a job
Run the job specified by it's identifier:

	rerun rundeck-run:job --id 4ece2781-bc42-43c5-93b0-46638a52fed5
    * 977 execution - [myproject: myjob] - running - 7s average-duration - by alexh

The command prints execution info, separated by hyphens:

* ExecId: The first number is the execution identifier (eg `977`).
* Job project and name: (eg, `[myproject: myjob]`)
* Status: Execution state: (eg `running`).
* Average duration: Estimated time for job to complete (eg. `7s`)
* User: The owner of the api-token that executed the command,  (eg, `by alex`)


#### Override nodefilters and pass arguments

You can override the nodefilters and pass arguments using the `--filter` and `--args` options:

	rerun rundeck-run:job --id 4ece2781-bc42-43c5-93b0-46638a52fed5 \
		--filter 'tags:www' --args '-optA valueA'


See the *status* command to get status about an execution.
