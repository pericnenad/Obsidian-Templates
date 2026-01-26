<%*
// Define the path for the new file
const newFolderPath = "Personal Daily"; 
const newFileName =  `Personal, ${tp.date.now("dddd, DD-MMM-YYYY")}`;

// Combine to form the full file path
const newFilePath = `${newFolderPath}/${newFileName}`;
const existing = tp.file.find_tfile(newFilePath);

// Find the template file
const templatePath = "Templates/Personal Note";
const templateFile = tp.file.find_tfile(templatePath);

// Read the template content and create a new file
if (templateFile) {
    if (existing) {
        // File exists - Open it in new tab
        await app.workspace.getLeaf(true).openFile(existing);
    }
    else {
        //File does not exist - Create it
        console.log("Creating: " + newFilePath);
        await tp.file.create_new(templateFile, newFileName, true, newFolderPath);
    } 
} else {
    // No Template - Barf and throw an error!
    console.log("Template file not found:", templatePath);
}
%>