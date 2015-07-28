Use *rundeck-exec* to run jobs, get their status and obtain execution output.


### Common options for connecting to rundeck
The two options below are used by the rundeck-exec commands. You can set environment variable

* --server-url <"${SERVER_URL:-}">: "rundeck base url"
* --api-token <${API_TOKEN:-}>: "the API access token"--api-token <>

They default to environment variables which you can set so you don't have to type them as command line options:

	export SERVER_URL=http://localhost:4440
	export API_TOKEN=xxxxxxxxxxxxxxxxxxx

Example:

	rerun rundeck-exec:status --id 123; # Env vars used for --server-url and --api-token.


