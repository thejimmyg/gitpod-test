# gitpod-test

## Getting started on GitPod

1. Create a git repo on GitHub - mine is called `github.com/thejimmyg/gitpod-test`

2. Set up a workspace on GitPod and link your repository.

3. In the GitPod terminal run these commands to link your Go module into the location Go expects. **WARNING: You must follow the step to link your project git repo into ~/go/pkg/<repopath>` using the `ln` command below otherwise the go tools won't work properly.**

```sh
gitpod /workspace/gitpod-test (main) $ pwd
/workspace/gitpod-test
gitpod /workspace/gitpod-test (main) $ echo $HOME
/home/gitpod
gitpod /workspace/gitpod-test (main) $ go version
go version go1.22.2 linux/amd64
gitpod /workspace/gitpod-test (main) $ mkdir -p ~/go/pkg/github.com/thejimmyg
gitpod /workspace/gitpod-test (main) $ ln -s /workspace/gitpod-test ~/go/pkg/github.com/thejimmyg/gitpod-test
gitpod /workspace/gitpod-test (main) $ go mod init github.com/thejimmyg/gitpod
go: creating new go.mod: module github.com/thejimmyg/gitpod-test
go: to add module requirements and sums:
        go mod tidy
```

4. Write your code, install dependencies and run your server:

```sh
gitpod /workspace/gitpod-test (main) $ mkdir cmd
gitpod /workspace/gitpod-test (main) $ vim cmd/main.go
gitpod /workspace/gitpod-test (main) $ go mod tidy 
go: finding module for package github.com/thejimmyg/greener
go: downloading github.com/thejimmyg/greener v0.1.1
go: found github.com/thejimmyg/greener in github.com/thejimmyg/greener v0.1.1
go: downloading github.com/Kodeworks/golang-image-ico v0.0.0-20141118225523-73f0f4cfade9
go: downloading github.com/andybalholm/brotli v1.1.0
go: downloading golang.org/x/image v0.15.0
gitpod /workspace/gitpod-test (main) $ go run cmd/main.go
2024/05/08 09:53:11 Server listening on :8000
```

5. Open the port to see the running server.


## Getting started on a physical machine

1. Create a git repo on GitHub - mine is called `github.com/thejimmyg/gitpod-test` and initialise it locally in the `~/go/pkg` directory. **WARNING: You must keep your git repos in the right place in ~/go/pkg/<repopath>` (or link them there) otherwise the go tools won't work properly.**

```sh
$ mkdir -p ~go/pkg/github.com/thejimmyg/gitpod-test
$ cd ~/go/pkg/github.com/thejimmyg/gitpod-test/
$ echo "# gitpod-test" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin git@github.com:thejimmyg/gitpod-test.git
$ git push -u origin main
Initialized empty Git repository in /home/james/go/pkg/github.com/thejimmyg/gitpod-test/.git/
[main (root-commit) 8d3731e] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 220 bytes | 220.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:thejimmyg/gitpod-test.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

2. Make changes:

```sh
$ mkdir cmd
$ vim cmd/main.go
$ go mod tidy 
go: finding module for package github.com/thejimmyg/greener
go: downloading github.com/thejimmyg/greener v0.1.1
go: found github.com/thejimmyg/greener in github.com/thejimmyg/greener v0.1.1
go: downloading github.com/Kodeworks/golang-image-ico v0.0.0-20141118225523-73f0f4cfade9
go: downloading github.com/andybalholm/brotli v1.1.0
go: downloading golang.org/x/image v0.15.0
$ go run cmd/main.go 
2024/05/08 09:53:11 Server listening on :8000
```
