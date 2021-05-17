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
hugo serve -w --config config.yaml -v  --disableFastRender  --bind=0.0.0.0 -D
```

#### Creating new posts

To create a new post in `mab` run (in a container)

```
hugo new post/mab/<title-of-new-post>/<title-of-new-post>.md
```
You can modify the newly created file now. First change the
`parent: <section>-news` to the actual topic.
In the `mab` example this would be `parent: mab-news`. <br>
This will sort the new post in the according section in the overview.

After adding some content you can run hugo to check, if your article
meets your expectations. Therefore you need to set `draft: false` and run
`hugo serve` or run `hugo serve -D` if you want to keep the draft status
of your article


To add one image to the top of all posts of a topic just place a hero.svg in
the root of that topic.

For an individual image for a post create a directory in that topic for that
post and place a `hero.svg` there, as well as the post's markdown file
