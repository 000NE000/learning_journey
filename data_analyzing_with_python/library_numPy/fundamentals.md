
###### Syntax
- Arrays are a special type of list that allows us to store values in an organized manner.
- An array can be created by either defining it directly using np.array() or by importing a CSV using np.genfromtxt('file.csv', delimiter=',').
- An operation (such as addition) can be performed on every element in an array by simply performing it on the array itsel
- Elements can be selected from arrays using their index and array locations, both of which start at 0.
- Logical operations can be used to create new, more focused arrays out of larger arrays.
###### Statistics in numPy


- Using the `np.sort` method to locate outliers.
- Calculating central positions of a dataset using `np.mean` and `np.median`.
- Understanding the spread of our data using percentiles and the interquartile range.
- Finding the standard deviation of a dataset using `np.std`.

- What is a histogram and how to map one using Matplotlib
- How to identify different dataset shapes, depending on peaks or distribution of data
- The definition of a normal distribution and how to use NumPy to generate one using NumPy’s random number functions
- The relationships between normal distributions and standard deviations
- The definition of a binomial distribution


#### caution
`a = [ [[1,2],[3,4]] , [[5,6],[7,8]] ]`
`print(np.mean(a, axis = 2))`  # axis = 2 : 1 -> 2 or 3 -> 4 or 5 -> 6 or 7 -> 8 
/*
[[1.5 3.5]
 [5.5 7.5]]
*/
`print(np.mean(a, axis = 1))` // # axis = 1 : [1,2] -> [3,4] or [5,6] -> [7,8]
/*
[[2. 3.]
 [6. 7.]]
 */
`print(np.mean(a, axis = 0))` // # axis = 0 : [[1,2], [3,4]] -> [[5,6], [7,8]]
/*
[[3. 4.]
 [5. 6.]]
*/

