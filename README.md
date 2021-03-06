
## Build

Build the project

```sh
make deps
make build
```

Creates Docker image `drone/drone-clone-git`

```sh
sudo make docker
```

## Usage

Clone a commit

```sh
./drone-clone-git <<EOF
{
	"clone" : {
		"branch": "master",
		"remote": "git://github.com/drone/drone",
		"dir": "/tmp/drone",
		"ref": "refs/heads/master",
		"sha": "436b7a6e2abaddfd35740527353e78a227ddcb2c"
	}
}
EOF
```

Clone a pull request

```sh
{
	"clone" : {
		"branch": "master",
		"remote": "git://github.com/drone/drone",
		"dir": "/tmp/drone",
		"ref": "refs/pull/877/merge",
		"sha": "8d6a233744a5dcacbf2605d4592a4bfe8b37320d"
	}
}
```

Clone a tag

```sh
./drone-clone-git <<EOF
{
	"clone" : {
		"branch": "master",
		"remote": "git://github.com/drone/drone",
		"dir": "/tmp/drone",
		"sha": "339fb92b9629f63c0e88016fffb865e3e1055483",
		"ref": "refs/tags/v0.2.0"
	}
}
EOF
```