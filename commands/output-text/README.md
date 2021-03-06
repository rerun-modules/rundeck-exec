
### Examples

Export the server url and api-token so you dont have to set them as command options:

	export SERVER_URL=http://localhost:4440
	export API_TOKEN=xxxxxxxxxxxxxxxxxxx

If you run a job via *rundeck-exec:job* use the number in the first field of output:

	rerun rundeck-exec:job --id 4ece2781-bc42-43c5-93b0-46638a52fed5
    * 977 execution - [myproject: myjob] - running - 7s average-duration - by alexh

The first number `977` is the execution identifier.

When the job succeeds the status will change from 'running' to 'succeeded':

	rerun rundeck-exec:status --id 977
	* 977 execution - [myproject: myjob] - succeeded - 7s duration

You can then get the output

	rerun rundeck-exec:output-text --id 977
	output from my job
	output from my job
	output from my job
	output from my job

#### Get the last lines

You can specify how many lines of the execution output to get via the `--last-lines <>` option:

	rerun rundeck-exec:output-text --id 977 --last-lines 1
	output from my job

#### Format

By default, 'text' is the output format. This is the output generated by each of the command steps.
It does not include execution metadata. This is available as xml or json

	rerun rundeck-exec:output-text --id 977 --last-lines 1 --format xml

Will produce output similar to:

	<output>
	  <id>977</id>
	  <offset>7397</offset>
	  <completed>true</completed>
	  <execCompleted>true</execCompleted>
	  <hasFailedNodes>false</hasFailedNodes>
	  <execState>succeeded</execState>
	  <lastModified>1436828109000</lastModified>
	  <execDuration>7800</execDuration>
	  <percentLoaded>100</percentLoaded>
	  <totalSize>403</totalSize>
	  <entries>
	    <entry time='15:55:02' 
	    	absolute_time='2015-07-13T22:55:02Z' 
	    	log='output from my job' 
	    	level='NORMAL' 
	    	user='alex' 
	    	command='' 
	    	stepctx='1' 
	    	node='rundeck1' />
	    	.
	    	.
	  </entries>
	</output>

