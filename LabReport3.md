# Lab Report 3 - Bugs and Commands

## Part 1 - Bugs
For my bug, I have chosen the `reverseInPlace` method in the `ArrayExamples.java` file. 

### Failing input:
```java
#Buggy method from ArrayExamples.java

# Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

#JUnit test with failing input from ArrayTests.java

@Test 
	public void testReverseInPlaceA() {
    int[] input1 = { 3, 4, 5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 4, 3}, input1);
	}
```

### Passing input:
```java
#Buggy method from ArrayExamples.java

# Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

#JUnit test with passing input from ArrayTests.java

@Test 
	public void testReverseInPlace() {
    int[] input1 = {8};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{8}, input1);
	}

```

### Symptoms:
![Image](scLR3/BugSymptoms.png)

### The bug, before and after fixing:
```java
#The method 'reverseInPlace' with no changes, before fixing

  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

#The method 'reverseInPlace' with changes, after fixing

static void reverseInPlace(int[] arr) {
    int temp = 0;
    for(int i = 0; i < (arr.length/2); i += 1) {
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
Before the fix, the method would overwrite the values in the array that need to be assigned to a new index, producing a "reversed" array with incorrect values. After the fix, the original value of an element is preseved in a temporary variable, and then swapped with the value in the element of the intended index. Using this method, only half of the array's length is iterated through, since the values are being "swapped" instead of just being overwritten.



## Part 2 - Researching Commands
I have chosen to research the `grep` command. 

*Note: For simplicity's sake, and to avoid having to do too much repition, I used the following bash script for my first three command options.*
```
# optionTest.sh
find $1 > optionSearchResults.txt
grep $2 "$3" optionSearchResults.txt
```

### `grep` command options:
* `--color`

```
#Test 1 command
$ bash optionTest.sh technical/911report --color r-1

#Test 1 output
technical/911report/chapter-1.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt

#Test 2 command
bash optionTest.sh technical/government/Media --color Barnes

#Test 2 output
technical/government/Media/Barnes_new_job.txt
technical/government/Media/Barnes_pro_bono.txt
technical/government/Media/Barnes_Volunteers.txt

```
*Note: Because of the nature of this option, and the environment that I am presenting the information in, the text does not actually change in color. When I ran these tests, the respective search/match arguments in each result were changed to the color red. (e.g. In test 1, the "r-1" at the end of "chapter" and "Barnes" after "Media/" in test 2.*

This option changes the color of the text/phrase used to match, making it very clear to see why a file was selected for a match. This could prove especially useful to confirm you aren't make any sort of case-sensitivity mistakes, typos, or a search phrase that is too vague/general.

* `-v, --invert-match` 
```
#Test 1 command
bash optionTest.sh technical/911report -v "chapter"

#Test 1 output
technical/911report
technical/911report/preface.txt

#Test 2 command
bash optionTest.sh technical/plos -v "journal"

#Test 2 output
technical/plos
technical/plos/pmed.0010008.txt
technical/plos/pmed.0010010.txt
technical/plos/pmed.0010013.txt
technical/plos/pmed.0010021.txt
technical/plos/pmed.0010022.txt
technical/plos/pmed.0010023.txt
technical/plos/pmed.0010024.txt
technical/plos/pmed.0010025.txt
technical/plos/pmed.0010026.txt
technical/plos/pmed.0010028.txt
technical/plos/pmed.0010029.txt
technical/plos/pmed.0010030.txt
technical/plos/pmed.0010034.txt
technical/plos/pmed.0010036.txt
technical/plos/pmed.0010039.txt
technical/plos/pmed.0010041.txt
technical/plos/pmed.0010042.txt
technical/plos/pmed.0010045.txt
technical/plos/pmed.0010046.txt
technical/plos/pmed.0010047.txt
technical/plos/pmed.0010048.txt
technical/plos/pmed.0010049.txt
technical/plos/pmed.0010050.txt
technical/plos/pmed.0010051.txt
technical/plos/pmed.0010052.txt
technical/plos/pmed.0010056.txt
technical/plos/pmed.0010058.txt
technical/plos/pmed.0010060.txt
technical/plos/pmed.0010061.txt
technical/plos/pmed.0010062.txt
technical/plos/pmed.0010064.txt
technical/plos/pmed.0010066.txt
technical/plos/pmed.0010067.txt
technical/plos/pmed.0010068.txt
technical/plos/pmed.0010069.txt
technical/plos/pmed.0010070.txt
technical/plos/pmed.0010071.txt
technical/plos/pmed.0020002.txt
technical/plos/pmed.0020005.txt
technical/plos/pmed.0020007.txt
technical/plos/pmed.0020009.txt
technical/plos/pmed.0020015.txt
technical/plos/pmed.0020016.txt
technical/plos/pmed.0020017.txt
technical/plos/pmed.0020018.txt
technical/plos/pmed.0020019.txt
technical/plos/pmed.0020020.txt
technical/plos/pmed.0020021.txt
technical/plos/pmed.0020022.txt
technical/plos/pmed.0020023.txt
technical/plos/pmed.0020024.txt
technical/plos/pmed.0020027.txt
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020033.txt
technical/plos/pmed.0020034.txt
technical/plos/pmed.0020035.txt
technical/plos/pmed.0020036.txt
technical/plos/pmed.0020039.txt
technical/plos/pmed.0020040.txt
technical/plos/pmed.0020045.txt
technical/plos/pmed.0020047.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020050.txt
technical/plos/pmed.0020055.txt
technical/plos/pmed.0020059.txt
technical/plos/pmed.0020060.txt
technical/plos/pmed.0020061.txt
technical/plos/pmed.0020062.txt
technical/plos/pmed.0020065.txt
technical/plos/pmed.0020067.txt
technical/plos/pmed.0020068.txt
technical/plos/pmed.0020071.txt
technical/plos/pmed.0020073.txt
technical/plos/pmed.0020074.txt
technical/plos/pmed.0020075.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0020085.txt
technical/plos/pmed.0020086.txt
technical/plos/pmed.0020088.txt
technical/plos/pmed.0020090.txt
technical/plos/pmed.0020091.txt
technical/plos/pmed.0020094.txt
technical/plos/pmed.0020098.txt
technical/plos/pmed.0020099.txt
technical/plos/pmed.0020102.txt
technical/plos/pmed.0020103.txt
technical/plos/pmed.0020104.txt
technical/plos/pmed.0020113.txt
technical/plos/pmed.0020114.txt
technical/plos/pmed.0020115.txt
technical/plos/pmed.0020116.txt
technical/plos/pmed.0020117.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0020120.txt
technical/plos/pmed.0020123.txt
technical/plos/pmed.0020140.txt
technical/plos/pmed.0020144.txt
technical/plos/pmed.0020145.txt
technical/plos/pmed.0020146.txt
technical/plos/pmed.0020148.txt
technical/plos/pmed.0020149.txt
technical/plos/pmed.0020150.txt
technical/plos/pmed.0020155.txt
technical/plos/pmed.0020157.txt
technical/plos/pmed.0020158.txt
technical/plos/pmed.0020160.txt
technical/plos/pmed.0020161.txt
technical/plos/pmed.0020162.txt
technical/plos/pmed.0020180.txt
technical/plos/pmed.0020181.txt
technical/plos/pmed.0020182.txt
technical/plos/pmed.0020187.txt
technical/plos/pmed.0020189.txt
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0020194.txt
technical/plos/pmed.0020195.txt
technical/plos/pmed.0020196.txt
technical/plos/pmed.0020197.txt
technical/plos/pmed.0020198.txt
technical/plos/pmed.0020200.txt
technical/plos/pmed.0020201.txt
technical/plos/pmed.0020203.txt
technical/plos/pmed.0020206.txt
technical/plos/pmed.0020208.txt
technical/plos/pmed.0020209.txt
technical/plos/pmed.0020210.txt
technical/plos/pmed.0020212.txt
technical/plos/pmed.0020216.txt
technical/plos/pmed.0020226.txt
technical/plos/pmed.0020231.txt
technical/plos/pmed.0020232.txt
technical/plos/pmed.0020235.txt
technical/plos/pmed.0020236.txt
technical/plos/pmed.0020237.txt
technical/plos/pmed.0020238.txt
technical/plos/pmed.0020239.txt
technical/plos/pmed.0020242.txt
technical/plos/pmed.0020246.txt
technical/plos/pmed.0020247.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020257.txt
technical/plos/pmed.0020258.txt
technical/plos/pmed.0020268.txt
technical/plos/pmed.0020272.txt
technical/plos/pmed.0020273.txt
technical/plos/pmed.0020274.txt
technical/plos/pmed.0020275.txt
technical/plos/pmed.0020278.txt
technical/plos/pmed.0020281.txt

```
This option ignores the usual output, and instead prints all of the lines that did _not_ match the given text/phrase. One scenario where this could be useful is if you needed to exclude a certain section or if you want to compare the non-matching lines without also having to look at the matching ones.

* `-m<NUM>, --max-count=<NUM>` 
```
#Test 1 command
bash optionTest.sh technical/plos -m10 "pmed"

#Test 1 output
technical/plos/pmed.0010008.txt
technical/plos/pmed.0010010.txt
technical/plos/pmed.0010013.txt
technical/plos/pmed.0010021.txt
technical/plos/pmed.0010022.txt
technical/plos/pmed.0010023.txt
technical/plos/pmed.0010024.txt
technical/plos/pmed.0010025.txt
technical/plos/pmed.0010026.txt
technical/plos/pmed.0010028.txt

#Test 2 command
bash optionTest.sh technical/biomed -m5 "2180-2"

#Test 2 output
technical/biomed/1471-2180-2-1.txt
technical/biomed/1471-2180-2-13.txt
technical/biomed/1471-2180-2-16.txt
technical/biomed/1471-2180-2-2.txt
technical/biomed/1471-2180-2-20.txt

```
This option sets a cap for the number of matched lines printed, up to the amount designated by the user. This would be incredibly useful for files with a lot of text and are sorted or ranked in some way. For example, if you were looking at a file containing the rankings of every participant at a gynastics meet, but you only want to list the top ten gymnasts with the last name "Smith", you could use `grep -m10 "Smith" <file name>`.

* `-c, --count` 
```
#Test 1 command
find technical/plos > inPlos.txt
find technical/biomed > inBiomed.txt
find technical/government > inGovernment.txt
grep -c ".txt" inPlos.txt inBiomed.txt inGovernment.txt


#Test 1 output
inPlos.txt:252
inBiomed.txt:837
inGovernment.txt:285

#Test 2 command
grep -c "02" inPlos.txt inBiomed.txt inGovernment.txt

#Test 2 output
inPlos.txt:208
inBiomed.txt:101
inGovernment.txt:28

```
This option ignores the usual output and instead prints a count of how many lines match, per input file. This would be useful especially with a series of files likely to contain large numbers of matches. For example, you could use it to search multiple hospitals' staff directories for the number of doctors, and display total doctors at each hospital. 
