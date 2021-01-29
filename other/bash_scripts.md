1. Renaming multiple files across multiple subdirectories. E.g. replace files with ‘old_name_1.doc’ with ‘new_name_1.doc’:

shopt -s globstar
rename 'old_name' new_name **

2. Copy multiple files called file_to_copy.doc and preserve parent folder structure:

find . -type f -name 'file_to_copy.doc' -exec cp -p --parents {} ./tmp ";"

3. Make multiple subfolders in all the folders in current directory

e.g. currently you have

./folderA ./folderB

You want:

./folderA/folder1 ./folderA/folder1 ./folderB/folder2 ./folderB/folder2

From the current directory ./ run:
for dir in */; do mkdir -- "$dir"/{anat,func}; done

4. Simple for loops are straightforward:

Move and rename multiple similarly name files around subfolders

for i in $(ls);
do mv $i/old_name.doc $i/subfolder/new_name.nii;
done

Use the folder name as part of the new filename:

for entry in ./*;
do mv "$entry"/subfolder/oldname.doc "$entry"/anat/"$entry"_newname.doc;
done

