# Polyquantum
_Open, collaborative, version-controlled research in quantum science_.

## About
_Polyquantum_ is an open platform for collaborative research in quantum science, structured as a GitHub repository.  
It enables researchers to:

- 💡 Share new research ideas openly  
- 🛠️ Collaborate on ongoing projects proposed by others  
- 📝 Preserve and track research contributions transparently  

A core feature of Polyquantum is the **transparent tracking of authorship**.  
By using [Git](https://it.wikipedia.org/wiki/Git_(software))’s distributed version control, every research step is permanently recorded in Markdown documents, ensuring proper recognition of contributors.  

👉 More details about Polyquantum can be found in [ABOUT.md](ABOUT.md).

## 🛠️ How to contribute to existing research ideas/projects/problems
1. Browse the [**Issues** section](https://github.com/andreamari/polyquantum/issues) to see existing research ideas/projects/problems.  
2. Interact and discuss by commenting on specific issues.  
3. To contribute original material (ideas, solutions, calculations, etc.) that is worth preserving in a (Git-tracked) document:  
   - 👉 Follow [this guide](docs/README.md) to create or edit a Markdown file in the subfolder `/docs/[ISSUE_NUMBER]/`.  For example, (for issue #1):
     ```
     /docs/1/2-contribution.md
     ```
   - In the document, add (or update) author(s) and affiliation(s).
4. If accepted, the new (or modified) document will be published in `/docs/[ISSUE_NUMBER]/` and permanently tracked by the Git system.
5. The document can be referenced as _Authors_, _Polyquantum 1.2 (2025)_ corresponding, in this example, to project #1, document #2, created in 2025.  



## 💡 How to share a new research idea/project/problem
1. Open a [new issue](https://github.com/andreamari/polyquantum_test/issues/new/choose) describing your idea/project/problem.
2. A new subfolder `/docs/[ISSUE_NUMBER]/` containing a `README.md` file (referencing your new issue) will be automatically created. 
3. To preserve your idea/project/problem in a (Git-tracked) document:  
   - 👉 Follow [this guide](docs/README.md) to create a new Markdown file in the subfolder `/docs/[ISSUE_NUMBER]/`.  For example, (for issue #1):
     ```
     /docs/1/1-idea.md
     ```
   - In the document, add author(s) and affiliation(s).
4. If accepted, the new document will be published in `/docs/[ISSUE_NUMBER]/` and permanently tracked by the Git system.
5. The new research idea/project/problem can be referenced as:
    - _Polyquantum 1_ (short notation similar to that used for [Polymath](https://en.wikipedia.org/wiki/Polymath_Project) projects);
    - _Authors_, _Polyquantum 1 (2025)_ corresponding, in this example, to project #1 as a whole, created in 2025;
    - _Authors_, _Polyquantum 1.1 (2025)_ corresponding, in this example, to project #1, specific document #1, created in 2025.

## Usage of Issues vs. Markdown files
- **Issues** are optimal for brainstorming, discussions, and quick comments. Authorship is not tracked by Git (similar to blog or social media posts).
- **Markdown files** are for more refined ideas/solutions/calculations worth preserving as a permanent record in the Git history. Such files are referenced, tracked, and version-controlled. Authorship is permanently preserved (similar to publishing on the [arXiv](https://en.wikipedia.org/wiki/ArXiv) repository).
