utserver
========
Run a uTorrent server in a Docker container.

Run container:
`docker run -d -p 6881:6881 -p 8080 $(pwd)/ut_data:/data --name utserver jad-b/utserver`
