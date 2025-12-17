```markdown
# 🚀 How to Create a New Release

Follow these steps to create a new release using **Git** and **GitHub Actions**:

---

## ✅ 1. Update the Changelog
Edit the file `debian/changelog` and add a new entry for the version you want to release:

```

cis-hardening (1.0-5) unstable; urgency=medium

*   Description of changes

\-- Your Name <your.email@example.com>  Tue, 16 Dec 2025 17:40:00 +0100

````

## ✅ 2. Commit the Changes
```bash
git add debian/changelog
git commit -m "Update changelog for version 1.0-5"
````

***

## ✅ 3. Push to Master

```bash
git push origin master
```

***

## ✅ 4. Create and Push a Tag

Use semantic versioning for the tag (e.g., `v1.0-5`):

```bash
git tag v1.0-5
git push origin v1.0-5
```

***

## ✅ 5. GitHub Actions Will Handle the Release

Once the tag is pushed:

*   The **Tagged-release.yml** workflow will:
    *   Build the `.deb` package.
    *   Generate the changelog from `debian/changelog`.
    *   Create a GitHub Release with the changelog as the description.
    *   Upload the `.deb` file as a release asset.

***