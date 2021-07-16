# SupraCoNeX Website

## Running the setup locally

### Getting Hugo

You can either install hugo locally on your machine or pull or build
 the docker image.

```
docker pull docker.io/ikstream/hugo:latest
```

#### Alternative

To build the image yourself, clone the github repository and run

```
git clone https://github.com/ikstream/hugo-docker.git hugo
cd hugo && docker build -t hugo .
```

### Run Hugo
If you installed Hugo locally, you can just run the commands. If you use docker,
start the container first

```
docker run --name hugo -it -p 1313:1313 -v $(pwd):/src/ --rm docker.io/ikstream/hugo:latest
```

or if you build the image yourself run:

```
docker run --name hugo -it -p 1313:1313 -v $(pwd):/src/ --rm hugo
```

#### Serving the current site

To serve the current state of the site or for later changes you need hugo
available.

```
hugo serve -w --config config.toml -v  --disableFastRender  --bind=0.0.0.0 -D
```

#### Creating new posts

To create a new post with the title `Best Entry` run

```
hugo new blog/best-entry.md
```

or with the docker

```
docker run -it -p 1313:1313 -v $(pwd):/src/ --rm hugo hugo new blog/best-entry.md

```

You can edit the newly created blog post at
`content/english/blog/best-entry.md`

After adding some content you can run hugo to check, if your article
meets your expectations. Therefore you need to set `draft: false` and run
`hugo serve` or run `hugo serve -D` if you want to keep the draft status
of your article

If you use the author tag, please provicde a small description text in
`content/english/author`
