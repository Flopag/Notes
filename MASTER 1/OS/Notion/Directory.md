# Directory

Directory is a node of the **directory structure** that contains information about files. All directories of the directory structure contains information about all files. Directory is used to be more efficient, be more convenient to users and have a better organisation (**grouping**)

Directory structure keep all information about [Files](File.md) on the [disk](Magnetic%20disks.md) (directory structure is itself on the [disk](Magnetic%20disks.md))

![](attachments/Pasted%20image%2020230614095135.png)

Directory operations :

- Search for a [File](File.md)
- Create a [File](File.md)
- Delete a [File](File.md)
- List a directory
- Rename a [File](File.md)
- Traverse the [File system](File%20system.md)

## Single-Level directory

One folder per user

There is not grouping possible $\rightarrow$ bad

![](attachments/Pasted%20image%2020230614101324.png)

## Two-Level Directory

There is no grouping possibilities but users can have multiple directories $\rightarrow$ better

![](attachments/Pasted%20image%2020230614101554.png)

## Tree-Structured Directories

Tree-structured directories is infinite-level directory

Grouping is possible and it is efficient to search in it

To navigate, we use **path name** (for exemple : /bin/mail/copy/all) that can be **absolute** or **relative**

Suppress a directory will suppress all [files](File.md) and directories in it

![](attachments/Pasted%20image%2020230614101719.png)

## Acyclic-graph directory

Tree-structured directories but with shared sub-directories and [files](File.md). [File](File.md) and directories are linked by **links** (pointers). Links have names, so, to find a [File](File.md) by a [File](File.md) name, follow the link with the same name (resolve the link)

Suppress a directory will suppress only links

Every time a new link is added use a cycle detection algorithm to determine if there leads to a loop (we don't want them)

![](attachments/Pasted%20image%2020230614102949.png)