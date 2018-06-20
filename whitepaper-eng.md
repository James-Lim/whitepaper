## commitground

Commitgrond is a development platform, and it offers rewards by own evaluation system. By the reward system, contributors can get rewards with Gerritium, the primary currency of commitground. Now, let's explore how we use commitground platform for our development projects.

### How to use Commitground

#### Starting a projects

```javascript
const {client} = require('commitground')
client.startPorject({
    type: "General" | "GPT",
    name: "ProjectName",
    repoistory: "Project repository's hosting information" // e.g. "https://commitground.com/projects/my-project"
})
```

##### type

Projects are separated into two types.

1. General Software Projects
2. GPT App

General Software Project means just common type which covers all kind of software. On the other hand, GPT App means specifically a decentralized application project which implements own token economy by issuing tokens based on GPT(Gerritium Project Token). We will dive into more detail about GPT App at [here](#Gerritium-Project-Token).

##### name

You can name the project using alphabets, numbers and '-', '\_'.

##### repository

Commitground stores data not only on the ethereum network but also the additional external source code repositories. On the ethereum network, only the hash values of project commit tree are written, and they are used to check whether the source codes being served by external repositories have same hash values with the written on the ethereum network. Also, we can designate the repositories like `git remote add 3rdparty git://yourhost/repository`.

> **Directory structure of common git project**
>
> Generally, a git project has a following directory structure.
>
>```bash
>.git
>├── HEAD
>├── config
>├── description
>├── hooks
>├── index
>├── info
>├── modules
>├── objects
>└── refs
>```
>
> Here, in the *objects* directory, source codes are stored being distributed and categorized by commit hash values. We write all the data except the *objects* directory on the ethereum network. First, it is too expensive to write all the source code data. Second, it is cryptologically safe to compare the hash values because git creates the hash using the previous commit's hash, author information, and also date information. Finally, in case of an open source project, by the existence of many clones, it is easy to detect the forgery, and in case of a private project, it is protected on the protocol level.

You can choose the repository services among the followings,

1. Self hosted server

   You can operate your own repository server with [git protocols](https://git-scm.com/book/gr/v2/Git-on-the-Server-The-Protocols). And also we provides a [docker image](linkhere)(Link should be updated) for self hosting.

2. Commitground's repository service

   Commitground provides a managed repository service. It is well integrated with the commitground platform. If you are running an open source project, you can use the service as free. It is convenient to get the rewards directly, when you get evaluations by the community.

3. 3rd parties

   Github and Gitlab are the typical examples of 3rd party repository services. In this case, to get rewards under the evaluation by the community, you have to install the plugins or browser extensions.

   [Starts with a github repository]()(link should be updated)
   [Starts with a gitlab repository]()(link should be updated)
