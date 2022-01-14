# How-to-restrict-access-to-the-master-branch-in-Git

<Git itself does not have such feature, but many hosting providers do. This is generally known as branch protection. There is no way to prevent read access as far as I know.>

Using Bitbucket
------------------
Bitbucket allows a lot of customization for the actions to prevent by branch protection. To protect a branch:

- Go to a repository in a project.

- Choose Settings → Branch permissions.

- Click Add permission.

- In the Branches field, select either Branch name, Branch pattern, or Branching model.

- Branch name - select an existing branch by name.

- Branch pattern - specify a branch using branch pattern syntax for matching branch names.

- Branching model - select the branch type to restrict access to.

- Select the type of actions you want to prevent.
- Branch deletion - prevents branch and tag deletion.

- Rewriting history - prevents history rewrites on the specified branch(es) - for example by a force push or rebase.

- Changes without a pull request - prevents pushing changes directly to the specified branch(es); changes are allowed only with a pull request.

- All modifications - prevents pushes to the specified branch(es) and restricts creating new branches matching the specified branch(es) or pattern.

>Optional: Add exemptions for any of the selected restrictions. Adding a user or group as an exemption means that it will not apply to them. This is not required; not adding any exemptions means the restriction will apply to everyone.

- Click Create to finish.

Source visit: https://confluence.atlassian.com/bitbucketserver/using-branch-permissions-776639807.html

Using GitHub
------------------

A repository can have multiple protected branch rules that affect the same branches.

>Protected branches are available only in public repositories with GitHub Free.

Protected branch in GitHub can be configured to require:
```
pushes to be made via pull requests and reviewed before being merged,

other branches to pass status check before being merged,

commits to be signed,

history to be linear,

that the above rules are enforced even for administrators,

that pushes come from specific people, teams or applications,

Force pushes and deletions can be allowed independently.
```
To protect a branch:

- On GitHub, navigate to the main page of the repository.

- Under your repository name, click Settings.

- In the left menu, click Branches.

- Next to "Branch protection rules", click Add rule.

- Under "Branch name pattern", type the branch name or pattern you want to protect (Impacted branches are listed and counted).

- Configure specific branch rule settings if needed.

- Click Create or Save changes.

Source Visit : https://docs.github.com/en/github/administering-a-repository/about-protected-branches

Using GitLab
-------------
In GitLab, protecting a branch does the following:
```
it prevents its creation, if not already created, from everybody except users with Master permission
it prevents pushes from everybody except users with Master permission
it prevents anyone from force pushing to the branch
it prevents anyone from deleting the branch
```
To protect the branch:

- Navigate to the main page of the project.

- In the upper right corner, click the settings wheel and select Protected branches.

- From the Branch dropdown menu, select the branch you want to protect and click Protect.

- Once done, the protected branch will appear in the "Already protected" list.

- You can then allow some access to users with developer rights by checking "Developers can merge" or "Developers can push"

Source visit: http://docs.gitlab.com/ee/user/project/protected_branches.html
