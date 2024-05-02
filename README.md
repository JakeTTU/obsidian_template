# Setting Up a Private Note Repository with Obsidian

This guide will help you set up a private note repository using Obsidian while still being able to pull updates to the Obsidian configuration files from a public template repository.

## Steps

1. Create a new private repository to store your private notes.

2. Clone the private repository to your local machine:
```shell
   git clone https://github.com/your-username/private-repo.git
```
   
3. Add the Obsidian template repository as a remote named `template`:
```shell
   git remote add template https://github.com/JakeTTU/obsidian_template.git
```
   
4. Fetch the latest changes from the `template` remote:
```shell
   git fetch template
```
   
5. Merge the changes from the `template` remote into your local `main` branch:
```shell
   git merge template/main
```

6. Create a new branch for your private notes:
```shell
   git checkout -b private-notes
```

7. Configure the `private-notes` branch to push only to the private remote repository:
```shell
   git config branch.private-notes.remote origin
   git config branch.private-notes.pushRemote origin 
```

8. Configure the `private-notes` branch to never push to the `template` remote repository:
```shell
   git config branch.private-notes.pushRemote "no_push"
```
   
9. Create or modify the `.gitignore` file in the `private-notes` branch to include the sensitive information you want to track.

10. Commit the changes to the `.gitignore` file in the `private-notes` branch:
```shell
   git add .gitignore
   git commit -m "Update .gitignore for private notes"
```

11. Add and commit your private notes in the `private-notes` branch:
```shell
   git add your-private-notes.md
   git commit -m "Add private notes"
```

12. Push the `private-notes` branch to the private remote repository:
```shell
   git push -u origin private-notes
```

## Pulling Updates from the Template Repository

To pull updates to the Obsidian configuration files from the template repository:

1. Ensure you are on the `main` branch:
```shell
   git checkout main
```

2. Fetch the latest changes from the `template` remote:
```shell
   git fetch template
```

3. Merge the changes from the `template` remote into your local `main` branch:
```shell
   git merge template/main
```

4. Push the updated `main` branch to your private remote repository:
```shell
   git push origin main
```

## Merging Updates to Your Private Branch

After pulling updates to the `main` branch from the template repository, you can merge those updates into your `private-notes` branch:

1. Ensure you are on the `private-notes` branch:
```shell
   git checkout private-notes
```
   
2. Merge the changes from the `main` branch into your `private-notes` branch:
```shell
   git merge main
```

3. Resolve any merge conflicts if necessary.

4. Commit the merged changes:
```shell
   git commit -m "Merge updates from main branch"
```

5. Push the updated `private-notes` branch to your private remote repository:
```shell
   git push origin private-notes
```

## Acknowledgments

Special thanks to [psuzzi](https://github.com/psuzzi) for creating and sharing your awesome Obsidian config and plugins for this template repository!

## Note

Remember to exercise caution when working with sensitive information and ensure that your private repository is properly secured and accessible only to authorized individuals.