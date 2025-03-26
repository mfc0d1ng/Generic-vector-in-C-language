# Generic vector in C language
 A shared library which provides a set of functions for handling dynamic arrays in C. Note that the library doesn't provide methods for constructing and copying the vector elements because C isn't object-oriented programming language. User is responsible for constructing and copying the vector elements.

<h2>How to download?</h2>
You can download it here <a href="https://github.com/user-attachments/files/19468164/libvector.zip">here</a>

<h2>How to install?</h2>
 Unzip the downloaded file and move libvector.so to /usr/lib

 <h2>How to link?</h2>
 You can link the library to your C project as follows: gcc example.c -l vector <br>
And don't forget to include vector.h, note that linked_list.h depends on vector_details.h so keep both in the same directory.
