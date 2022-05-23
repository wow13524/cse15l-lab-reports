# Week 8 - Lab Report 4
This lab report aims to showcase the difference in implementation between my `markdown-parser` and that of another group's.

## Relevant Repositories
[This is a link to my `markdown-parser` repository](https://github.com/wow13524/markdown-parser).  
[This is a link to the other group's `markdown-parser` repository](https://github.com/khiemddang/markdown-parser).  

## Snippet 1
### Expected Output:
```
[`google.com, google.com, ucsd.edu]
```
### Test Code:
```
@Test
public void test_snippet_1() throws IOException{
    Path fileName = Path.of("snippet-1.md");
    String content = Files.readString(fileName);
    ArrayList<String> links = MarkdownParse.getLinks(content);
    assertArrayEquals(new Object[]{"`google.com","google.com","ucsd.edu"},links.toArray());
}
```
### My Output
```
test_snippet_1(MarkdownParseTest)
arrays first differed at element [0]; expected:<[`google].com> but was:<[url].com>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:285)
        at org.junit.Assert.assertArrayEquals(Assert.java:300)
        at MarkdownParseTest.test_snippet_1(MarkdownParseTest.java:52)
        ... 32 trimmed
Caused by: org.junit.ComparisonFailure: expected:<[`google].com> but was:<[url].com>
        at org.junit.Assert.assertEquals(Assert.java:117)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more

FAILURES!!!
```
### Other Group's Output
```
test_snippet_1(MarkdownParseTest)
array lengths differed, expected.length=3 actual.length=4; arrays first differed at element [0]; expected:<[`google].com> but was:<[url].com>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:285)
        at org.junit.Assert.assertArrayEquals(Assert.java:300)
        at MarkdownParseTest.test_snippet_1(MarkdownParseTest.java:54)
        ... 32 trimmed
Caused by: org.junit.ComparisonFailure: expected:<[`google].com> but was:<[url].com>
        at org.junit.Assert.assertEquals(Assert.java:117)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more

FAILURES!!!
```

## Snippet 2
### Expected Output:
```
[a.com, a.com(()), example.com]
```
### Test Code:
```
@Test
public void test_snippet_2() throws IOException{
    Path fileName = Path.of("snippet-2.md");
    String content = Files.readString(fileName);
    ArrayList<String> links = MarkdownParse.getLinks(content);
    assertArrayEquals(new Object[]{"a.com","a.com(())","example.com"},links.toArray());
}
```
### My Output
```
test_snippet_2(MarkdownParseTest)
array lengths differed, expected.length=3 actual.length=2; arrays first differed at element [1]; expected:<a.com(([))]> but was:<a.com(([]>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:285)
        at org.junit.Assert.assertArrayEquals(Assert.java:300)
        at MarkdownParseTest.test_snippet_2(MarkdownParseTest.java:60)
        ... 32 trimmed
Caused by: org.junit.ComparisonFailure: expected:<a.com(([))]> but was:<a.com(([]>
        at org.junit.Assert.assertEquals(Assert.java:117)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more

FAILURES!!!
```
### Other Group's Output
```
test_snippet_2(MarkdownParseTest)
arrays first differed at element [1]; expected:<a.com(([))]> but was:<a.com(([]>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:285)
        at org.junit.Assert.assertArrayEquals(Assert.java:300)
        at MarkdownParseTest.test_snippet_2(MarkdownParseTest.java:62)
        ... 32 trimmed
Caused by: org.junit.ComparisonFailure: expected:<a.com(([))]> but was:<a.com(([]>
        at org.junit.Assert.assertEquals(Assert.java:117)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more

FAILURES!!!
```

## Snippet 3
### Expected Output:
```
[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]
```
### Test Code:
```
@Test
public void test_snippet_3() throws IOException{
    Path fileName = Path.of("snippet-3.md");
    String content = Files.readString(fileName);
    ArrayList<String> links = MarkdownParse.getLinks(content);
    assertArrayEquals(new Object[]{"https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule"},links.toArray());
}
```
### My Output
```
test_snippet_3(MarkdownParseTest)
arrays first differed at element [0]; expected:<[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]> but was:<[
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
]>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:285)
        at org.junit.Assert.assertArrayEquals(Assert.java:300)
        at MarkdownParseTest.test_snippet_3(MarkdownParseTest.java:68)
        ... 32 trimmed
Caused by: org.junit.ComparisonFailure: expected:<[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]> but was:<[
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
]>
        at org.junit.Assert.assertEquals(Assert.java:117)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more

FAILURES!!!
```
### Other Group's Output
Test Passed!

## Post-Test Q & A
### Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.
I think there is a code change that can be done that, while admittedly is an imperfect approach, corrects the failed test for snippet 1.  It requires two static helper methods and a replacement of `markdown.indexOf` calls to one of these helper methods.
```
private static boolean isWithinInlineCode(String markdown,int end){
    String subMarkdown = markdown.substring(0,end);
    return (subMarkdown.length() - subMarkdown.replace("`","").length()) % 2 != 0;
}

private static int indexOfMarkdown(String markdown,String toFind,int index){
    do{
        index = markdown.indexOf(toFind,++index);
        System.out.println(index);
    }while(index >= 0 && isWithinInlineCode(markdown,index));
    return index;
}
```

### Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.
I do not think there is a small code change that can make my program work with nested paretheses, brackets, and escaped brakets.  The first line of snippet 2 has a nested link within another link.  It took a lot of refactoring to get this test to pass.  Even then, I don't think it holds up.
```
private static int countOccurences(String markdown,String target){
    return markdown.length() - markdown.replace(target,"").length();
}
...
private static int indexOfCloseParen(String markdown,int openParen){
    int index = markdown.indexOf(")",openParen);
    if(index == -1){
        return -1;
    }
    int occurrences = countOccurences(markdown.substring(openParen+1,index),"(");
    for(int i=0;i<occurrences;i++){
        index = markdown.indexOf(")",index+1);
    }
    return index;
}
```

### Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.
Yes, there is a small code change that makes my program work for snippet 3.  I first need to verify that there are no line breaks in either the text or url part of the link compound, as well as strip the link before adding it to the ArrayList of links to return.
```
//continue if there is a line break in the text
if(markdown.substring(openBracket+1,closeBracket).contains("\n\n")){
    continue;
}
//continue if there is a line break in the link
if(markdown.substring(openParen+1,closeParen).contains("\n\n")){
    continue;
}
...
toReturn.add(markdown.substring(openParen + 1, closeParen).strip());
```