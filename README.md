# Generic vector in C language
A shared library which provides a set of functions for handling dynamic arrays in C.

<h2>How to download?</h2>
You can download it here <a href="https://github.com/user-attachments/files/20149295/libvec.zip">here</a>

<h2>How to install?</h2>
 Unzip the downloaded file and move libvec.so to /usr/lib

 <h2>How to link?</h2>
 You can link the library to your C project as follows: gcc example.c -l vec
<br>
<h2> Examples </h2>

* Example A:

<pre>
<code class="language-c">
#include &lt;stdio.h&gt;
#include &lt;stdlib.h&gt;
#include "vector.h"

int main()
{
    /* Construct integers */
    vector integers = vector_new();

    for (size_t i = 101; i < 110; i++)
    {
        /* Add data to integers */
        vector_push_back(int, &integers, i);
    }

    /* Insert 100 at the beginning of integers */
    vector_insert(int, &integers, vector_begin(int, &integers), 100);
    
    /* Getting iterator that points to the first 
       element in integers */
    int* integers_it = vector_begin(int, &integers);
    
    /* Print contents of integers */
    printf("Vector integers contains: ");
    for (size_t i = 0; i < integers.size; i++)
    {
        printf("%i ", integers_it[i]);
    }

    /* Erase integers */
    vector_destructor(&integers);
    
    return EXIT_SUCCESS;
}
</code>
</pre>


* Example B:

<pre>
<code class="language-c">
#include &lt;stdio.h&gt;
#include &lt;stdlib.h&gt;
#include &lt;string.h&gt;
#include "vector.h"

/* Sort predicate */
int sort_fruits_predicate(const void* __ls, const void* __rs)
{
    return strcmp(*(const char **)__ls, *(const char **)__rs) > 0;
}

int main()
{
    /* Construct fruits */
    vector* fruits = vector_object();

    /* Add fruits to vector fruits */
    vector_push_back(const char*, fruits, "strawberry");
    vector_push_back(const char*, fruits, "apple");
    vector_push_back(const char*, fruits, "pineapple");
    vector_push_back(const char*, fruits, "banana");

    /* Sort fruits in ascending order */
    vector_sort(const char*, fruits, sort_fruits_predicate);

    /* Print contents of fruits */
    printf("Vector fruits after sorting: ");
    for (size_t i = 0; i < fruits->size; i++)
    {
        printf("%s ", vector_at(const char*, fruits, i));
    }

    /* Erase fruits */
    vector_delete(fruits);

    return EXIT_SUCCESS;
}
</code>
</pre>
