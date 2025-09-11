# A Quick Note About BOM in UTF-8
I recently encountered an error in CSV exports facing sales staff. They mentioned that addresses with foreign characters weren't showing up correctly. Here's what they were seeing:

<img width="222" height="50" alt="image" src="https://github.com/user-attachments/assets/852aa5e3-87d9-4e5b-bc82-a934ea6ce58d" />

Notice how basic latin letters are showing up correctly, but the japanese characters are being misread.

It turns out this is a problem with how speadsheet programs interpret character sets. Most modern programs natively default to utf-8 (the character set we're encoding these files in).

<img width="629" height="23" alt="image" src="https://github.com/user-attachments/assets/40965f51-8aef-4c15-98e4-5d274730b005" />

Unfortunately, not all programs adhere to this standard. Older programs and some western releases of software default to other encodings like Windows-1252 and ISO-8859-1. When one of these programs opens a UTF-8 encoded file, unless specified, it'll interpret the file using one of these incorrect standards. 

This was missed originally in this implementation because basic latin characters are encoded the same way across most common encoding standards. If the program uses the wrong standard, you'll often still get usable results:

<img width="200" height="49" alt="image" src="https://github.com/user-attachments/assets/fbd5de7b-bd86-4085-88ce-722cf62fc3a8" />

The problem arises when you encode characters outside of this standard range. Then you get funky results like this:

<img width="72" height="19" alt="image" src="https://github.com/user-attachments/assets/6d766160-f5af-43cf-be61-a20e3d964382" />

<img width="169" height="17" alt="image" src="https://github.com/user-attachments/assets/4010dfb5-4fc3-413e-bb6f-9a2e5b5232bb" />

<hr></hr>

To fix this, we can appead a byte order mark (BOM) to the beginning of the file.

<img width="381" height="87" alt="image" src="https://github.com/user-attachments/assets/618e62bb-bb0a-418f-84a5-9000f9e767ad" />

There a lot of technical history and details behind BOMs, but that stuff isn't actually relevant here. We prepend the `\uFEFF` BOM as a hint to the program that we're using UTF-8. That's it. The program doesn't need to interpret the text any special way other than switching to UTF-8 decoding.

With that change, we fixed the problem:

<img width="219" height="49" alt="image" src="https://github.com/user-attachments/assets/7dc42979-3c89-497c-8e74-329c53d85e1e" />

Happy sales team 👍
