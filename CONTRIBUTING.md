# Contributing

We welcome any contributions and are willing to help you get that 100% completion, making our project and your gaming experience better.

## Contribution Guide

Follow the steps below to contribute to the main repository via pull request. You can learn about the details of pull requests [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).


### 1. Fork the Official Repository

Firstly, you must visit the [perfect100 repository](https://github.com/lukojy3d/perfect100.git) and log into your account. The `fork` button is at the top right corner of the web page alongside buttons such as `watch` and `star`.

Now, you can clone your forked repository into your local environment.

```shell
git clone https://github.com/<YOUR-USERNAME>/perfect100.git
```

### 2. Create a New Branch

It would be best not to change your forked repository's main branch, as this might make upstream synchronization difficult. You can create a new branch with the appropriate name. General branch name format should start with `fix/` and `feat/`. `fix` is for minimal adjustments (similar to a bug fix), and `feat` is for adding a new feature, guide, game list, etc.

```shell
git checkout -b <NEW-BRANCH-NAME>
```

### 3. Running Golang (local development)

1. Set up Golang depending on your platform.
2. Add game title and id in [games.json](games.json). Example
```json
...
    {
      "id": "1091500",
      "name": "Cyberpunk 2077"
    }
...
```
_Game ID can be found on the steam store page or steamdb.info_
3. Do `go run .\build.go`. Remember that the OpenAI api key should be exported as an environment variable for a script to work properly.
4. Script will populate the achievement list and guide folder contents after a script successfully runs.

### 4. Making changes without running golang

Most parts of the process are automated by GitHub action to keep all information more structured. 

Sometimes there is no need to run Golang as you want to add a couple of game guides for existing games in which guide files are already generated. However, if you need to add a new game, this can be done with the following workflow:

1. Add game id and name to [games.json](/games.json). (game id can be found on the steam store page URL or steamdb.info).
2. Commit your changes and open a pull request.
3. Wait for GitHub actions to do the rest (it will generate an achievement list, achievement guides by completely inaccurate AI, and stats of players)

### 5. Code Commit to a fork

You can commit and push the changes to your local repository.

```shell
git add -A
git commit -m "<COMMIT-MESSAGE>"
git push
```

### 7. Open a Pull Request

You can now create a pull request on the GitHub webpage of your repository. As we like polished steam profiles, we also like neat Pull Requests and Issues! So we have a few requirements:

1. Use proper commit names (according to [requirements](.github/commitlint.config.js)):

- type is one of `games`, `guides`, `multi`, `tools`
- the subject is always Sentence-cased
- Examples when editing games.json
  - games: Add "Among Us"
- Examples when adding guides
  - guides: Create 'Cyberpunk 2077' 'Legends of the afterlife'
  - guides: Create all 'MultiVersus' achievement guides
- Examples when changing multiple categories
  - multi: Add 'Lost Ark' and change the readme
  - multi: Add 'Fall Guys' guides and update commitlint config
- Examples when changing scripts, readme, workflows, etc.
  - tools: Improve commitlint workflow
  - tools: Make build.go mo dynamic

2. Let's do quality over quantity! It's always better to take time and make clear, informative, and structured guides instead of confusing wallpaper-length paragraphs or simple lazy one-liners.

3. Use one commit per PR. Some functionalities depend on it, so if needed - squash those commits or even try using the --amend flag when committing. It's a very handy thing to learn!

## Create an issue

Not everyone is familiar with GitHub, and it might be difficult for first-time contributors to follow such a workflow. In such cases, write your content in an issue, and we will help you turn that issue into a pull request.