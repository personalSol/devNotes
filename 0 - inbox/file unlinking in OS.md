---
status: newBorn
related-links: 
created: 2025-06-02T09:17
updated: 2025-06-02T09:17
---
---

In an OS, files are stored with:

- **Metadata**: includes timestamp, size, permissions, disk location (e.g., inode in Linux), etc.
- **Data blocks**: actual content of the file stored on the disk.

When a file is deleted:

- The **file system unlinks the file** by removing its entry from the directory (i.e., removes the link to the metadata).
- The **metadata is marked as free** (or deleted, depending on the FS).
- The **data blocks are marked as available** for reuse, but not immediately erased.

Because the actual content remains on disk until overwritten, **file recovery tools can often retrieve deleted files** if the data hasn't been overwritten yet.