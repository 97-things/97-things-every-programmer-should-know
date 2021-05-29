# Data Type Tips

The reserved words `int`, `shortint`, `short`, and `smallint` are a few names, taken from only two programming languages, that indicate a two-byte signed integer.

The names and storage mechanisms for various kinds of data have become as varied as the colors of leaves in New England in the fall. This really isn't so bad if you spend all your time programming in just one language. However, if you're like most developers, you are probably using a number of languages and technologies, which requires you to write code to convert data from one data type to another frequently.

Many developers for one reason or another resort to using _variant_ data types, which can further complicate matters, require more CPU processing, and are usually abused. Variant data types definitely have their place but they are often abused. The fact is that a programmer should understand the strengths, weaknesses and implications of using any data type. One good example of where variants might be employed are functions specifically designed to accept and handle various types of data that might be passed into one or more variant parameters. One bad example of using variants would be to use them so frequently that language data type rules are effectively nullified.

You can ease data type complexity when writing conversions by using an apples to apples common reference point to describe data in much the same way that many countries with varied cultures and tongues have a common, standard language to speak. The benefit of designing your code around such an idea results in modular reusable code that makes sense and centralizes data conversion to one place.

The following data types are just commonplace subset of what is available and can store just about anything:

|boolean | _true_ or _false_ |

|single-byte char| |

|unicode char| |

|unsigned integer| 8 bit|

|unsigned integer|16 bit|

|unsigned integer|32 bit|

|unsigned integer|64 bit|

|signed integer|8 bit|

|signed integer|16 bit|

|signed integer|32 bit|

|signed integer|64 bit|

|float|32 bit|

|double|64 bit|

|string|undetermined length|

|string|fixed length|

|unicode string|undetermined length|

|unicode string|fixed length|

|unspecified binary object|undetermined length|

The trick is to write code to convert your various data types to your "common tongue" and alternately write code to convert them back. If you do this for the various systems in your organization, you will have a data-type conversion code base that can move data to and from every system you did this for. This will speed data conversion tremendously.

This same technique works for moving data to and from disparate database software, accounting SDK interfaces, CRM systems, and more.

Now, converting and moving complex data types such as record structures, linked lists, and database tables obviously complicates things. Nonetheless, the same principles apply. Whenever you create a staging area whose layout is well defined, like the data types listed above, and write code to move data into a structure from a given source as well as the mechanism to move it back, you create valuable programming opportunities.

To summarize, it's important to consider what each data type offers and their implications in the language they are used in. Additionally, when considering systems integrations where disparate technologies are in use, it is wise to know how data types map between the systems to prevent dataloss.

Most organizations are very aware of the fetters that vendor lock-in creates. By devising a common tongue for all your systems to speak in, you manufacture a powerful tool to loosen those bonds.

The details may be in the data, but the data is stored in your data types.

By [Jason P Sage](http://programmer.97things.oreilly.com/wiki/index.php/Jason_P_Sage)
