# Github Package Registry Gradle 

Example repo showing how to use GPR with a gradle based project.

See [the complete example.](gpr-example)

- Essentially followed: https://help.github.com/en/github/managing-packages-with-github-package-registry/configuring-gradle-for-use-with-github-package-registry
  - Add `maven-publish` plugin and `publishing` task to `build.gradle` file
  - Create github access token with `delete:packages`, `read:packages`, `repo`, and `write:packages` scopes
  - Bake access token into environment variables:

- e.g. on *nix systems:
```
export GPR_USER=<your_github_user>
export GPR_API_KEY=<your_github_access_token>
```

- Run publish task:
```
./gradlew publish
```

- Your package will be available at: 
  - https://github.com/<your_github_user>/<your_github_repo>/packages

## TODO
- Create a pipeline which automates the publish step
  - E.g. on pull request merge
  - BLOCKED because I don't have access to github actions beta
