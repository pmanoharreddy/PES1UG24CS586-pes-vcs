# PES1UG24CS586-pes-vcs

**Building PES-VCS — A Version Control System from Scratch**

---

## 📌 Objective

This project implements a simplified version control system similar to Git. It tracks file changes, stores snapshots efficiently using hashing, and maintains commit history.

---

## ⚙️ Platform

* Ubuntu / WSL (Linux)
* C programming language
* GCC compiler

---

## 🚀 Features Implemented

### Phase 1 — Object Storage

* Content-addressable storage using SHA-256
* Blob storage with deduplication
* Integrity verification using hash

### Phase 2 — Tree Objects

* Directory structure representation
* Tree serialization and parsing
* Deterministic tree generation

### Phase 3 — Index (Staging Area)

* Text-based index file
* File staging using `pes add`
* Status tracking (staged, unstaged, untracked)

### Phase 4 — Commits

* Commit creation with metadata
* Parent linking (history chain)
* Commit log traversal

---

## 📂 Project Structure

```
.pes/
├── objects/        # Stored blobs, trees, commits
├── refs/heads/     # Branch pointers
├── index           # Staging area
└── HEAD            # Current branch reference
```

---

## 🛠️ Commands Implemented

```bash
pes init              # Initialize repository
pes add <file>        # Stage file
pes status            # Show status
pes commit -m "msg"   # Create commit
pes log               # Show history
```

---

## 🔧 Build Instructions

```bash
make clean
make
```

---

## ▶️ Testing

### Phase 1

```bash
make test_objects
./test_objects
```

### Phase 2

```bash
make test_tree
./test_tree
```

### Full Flow

```bash
./pes init
./pes add file.txt
./pes commit -m "message"
./pes log
```

---

## 📸 Screenshots Included

![Phase 1](screenshots/1.png)
![Phase 1](screenshots/1b.png)

### Phase 2: Object storage tests
![Phase 2](screenshots/2.png)
![Phase 2](screenshots/2b.png)

### Phase 3: Object storage tests
![Phase 3](screenshots/3.png)
![Phase 3](screenshots/3b.png)

### Phase 4: Object storage tests
![Phase 4](screenshots/4.png)
![Phase 4](screenshots/4b.png)
![Phase 4](screenshots/4c.png)

---

## 🧠 Concepts Learned

* Content-addressable storage
* Hash-based integrity
* File system structures
* Version control internals
* Atomic file operations

---

## 📊 Commit History Requirement

✔ Minimum 5 commits per phase
✔ Clear and descriptive commit messages
✔ Demonstrates step-by-step development

---

## 📚 Analysis Answers

### Q5.1 (Checkout)

Checkout updates HEAD and replaces working directory with files from target commit.

### Q5.2 (Dirty Check)

Compare working directory with index; if mismatch, block checkout.

### Q5.3 (Detached HEAD)

HEAD points to commit directly. Commits exist but not linked to branch.

### Q6.1 (Garbage Collection)

Traverse all reachable commits and delete unreachable objects.

### Q6.2 (Race Condition)

GC may delete objects during commit. Avoid using locking and safe traversal.

---

## 👤 Author

**P Manohar Reddy**
PES1UG24CS586

---

## ✅ Status

✔ All phases implemented
✔ All tests passed
✔ End-to-end working
✔ Ready for submission
