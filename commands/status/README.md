### Examples

Export the server url and api-token so you dont have to set them as command options:

	export SERVER_URL=http://localhost:4440
	export API_TOKEN=xxxxxxxxxxxxxxxxxxx

If you run a job via *rundeck-run:job* use the number in the first field of output:

	rerun rundeck-run:job --id 4ece2781-bc42-43c5-93b0-46638a52fed5
    * 977 execution - [myproject: myjob] - running - 7s average-duration - by alexh

The first number `977` is the execution identifier.

Get status information about it:

	rerun rundeck-run:status --id 977
	* 977 execution - [myproject: myjob] - running - 5s elapsed (~70.0%)

The command prints execution info, separated by hyphens:

* ExecId: The first number is the execution identifier (eg `977`).
* Job project and name: (eg, `[myproject: myjob]`)
* Status: Execution state: (eg `running`).
* Time elapsed: Time duration since job execution started (eg. `5s`)
* Percent of average execution: The average duration is used to calculate an estimated percent completion (e.g., `~70%`).


When the job succeeds the status will change from 'running' to 'succeeded':

	rerun rundeck-run:status --id 977
	* 977 execution - [myproject: myjob] - succeeded - 7s duration
