# `custom-git-template-dir`

Replacement for standard functionality of [git hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)

Template directory instead of producing local repository-specific git hooks, calls global hooks with pre-configured directory

## How to test this setup?

1. Clone this repository

    ```sh
    git clone
    ```

2. Adjust env variables - **Remain** in same directory where you've executed `git clone` operation

    ```sh
    export GIT_TEMPLATE_DIR="$PWD/custom-git-template-dir/template-dir"
    export GIT_GLOBAL_HOOKS_PATH="$GIT_TEMPLATE_DIR/../example-global-hooks"
    ```

3. Create a new repository

    ```sh
    mkdir new-repo
    git init new-repo
    ```

4. Create a sample commit

    ```sh
    cd new-repo
    echo a >a
    git add .
    git commit -m"Initial commit"
    ```

5. You should see following message from [`example-global-hooks/post-commit`](./example-global-hooks/post-commit)

```txt
Hello from global post-commit hook
```

## Dislaimer

Use at your own risk
