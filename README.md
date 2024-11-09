# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

## Plagarism Statement

All exercises must contain the following statement:
“I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.”

## Note
I did not complete this excerise last semester as I am weak in probabilities, I consulted Ishita Patel to double check my math.

## Answer
Based on slide 34, we observe that the probability of selecting a bad pivot is the same as selecting a good pivot at 50%. So our goal is to see how middle-of-three selection compares, and it will be good to remember that the ideal pivot range is n/2 which is also based on the statement "Any good pivot creates two partitions of size at most 3n/4".

With the middle-of-three, we have the first, middle, and last elements chosen which could be less than the ideal pivot range, in the ideal pivot range, or greater than the ideal pivot range and these will be denoted as L,I,G respectively. Looking at all equally possible combinations of these pivots, we have $3^3$ possible permutations listed below separated out for clarity.

LLL, LLI, LLG, LIL, LII, LIG, LGL, LGI, LGG

ILL, ILI, ILG, IIL, III, IIG, IGL, IGI, IGG

GGL, GGI, GGG, GLL, GLI, GLG, GIL, GII, GIG

Now we can also sort them further into groups where they are unique permutations, or in other words, group the permutations together that have the same amounts of LIG but where the only difference is their order such as IGG,GGI, and GIG.

LLL

III

GGG

LLI, LIL, ILL

LLG, LGL, GLL

IIG, IGI, GII

IIL, ILI, LII

GGI, GIG, IGG

GGL, GLG, LGG

LIG, LGI, GIL, IGL, ILG, GLI

Then, using the image and details provided by slide 34, we can calculate probabilities for each of these groups of permutations(i.e 1/2 for good pivot, 1/4 for less than or greater than)

LLL = $({1}/{4})$

III

GGG

LLI, LIL, ILL

LLG, LGL, GLL

IIG, IGI, GII

IIL, ILI, LII

GGI, GIG, IGG

GGL, GLG, LGG

LIG, LGI, GIL, IGL, ILG, GLI

