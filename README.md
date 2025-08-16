# How to run the project

- Clone the project with submodules, as the theme of the blog is a Git submodule: 

```console
git clone --recurse-submodules <repository-url>
```

- Download and install [Hugo](https://gohugo.io/installation/). The version `v0.147.9` works fine. Later versions are not compatible with the theme (Blowfish) used by the blog for now.
- Run the following command to deploy the web locally:

```console
hugo server
```

- Access 