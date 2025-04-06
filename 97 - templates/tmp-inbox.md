<%*
const filename = app.workspace.activeLeaf.view.file.name;

if (filename.startsWith("tG")) {
    const baseName = filename.replace(/\.md$/, "");
    const newLocation = `96 - tags/${baseName}.md`;
    await app.vault.rename(app.workspace.activeLeaf.view.file, newLocation);
} else {
    // Use Obsidian link format with double brackets for template inclusion
    tR += await tp.file.include("[[tmp-full-note]]");
}
%>