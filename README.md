#  Mean and variance of a discrete  distribution


# Aim : 

To find mean and variance of arrival of objects from the feeder using probability distribution


# Software required :  

Python and Visual components tool

# Theory:

The expectation or the mean of a discrete random variable is a weighted average of all possible
values of the random variable. The weights are the probabilities associated with the corresponding values. 
It is calculated as,

![image](https://user-images.githubusercontent.com/103921593/192938463-e34177f4-f188-48a0-bda2-8f6d1d660ed2.png)

The variance of a random variable shows the variability or the scatterings of the random variables.
It shows the distance of a random variable from its mean. It is calcualted as

![image](https://user-images.githubusercontent.com/103921593/192938695-99fedc01-34d5-4d36-84df-5880e766ed0c.png)


# Procedure :

1. Construct frequency distribution for the data

2. Find the  probability distribution from frequency distribution.

3. Calculate mean using 
   
   ![image](https://user-images.githubusercontent.com/103921593/192940431-03b81777-c54d-4286-b4f4-82dfe7666b4c.png)

4. Find  
   
      ![image](https://user-images.githubusercontent.com/103921593/192940255-2d9dd746-6875-4a6d-877b-6da6cdb96ab1.png)

5.  Calculate variance using 
  
      ![image](https://user-images.githubusercontent.com/103921593/192942852-913550a9-fabe-4a55-b956-0487b18bbd97.png)


# Experiment :

![image](https://user-images.githubusercontent.com/103921593/229993174-5b67e57e-3e01-4ac4-9f83-410a932b22bf.png)

# Program :

def construct_frequency_distribution(data):
    frequency_distribution = {}
    for value in data:
        if value in frequency_distribution:
            frequency_distribution[value] += 1
        else:
            frequency_distribution[value] = 1
    return frequency_distribution

def convert_to_probability_distribution(frequency_distribution, total_count):
    probability_distribution = {value: count / total_count for value, count in frequency_distribution.items()}
    return probability_distribution

def calculate_mean(probability_distribution):
    mean = sum(value * probability for value, probability in probability_distribution.items())
    return mean

def calculate_variance(probability_distribution, mean):
    variance = sum((value - mean) ** 2 * probability for value, probability in probability_distribution.items())
    return variance

def main():

    data = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 5]
    
    frequency_distribution = construct_frequency_distribution(data)
    total_count = sum(frequency_distribution.values())
    
    probability_distribution = convert_to_probability_distribution(frequency_distribution, total_count)
   
    mean = calculate_mean(probability_distribution)

    variance = calculate_variance(probability_distribution, mean)
    
    print("Mean:", mean)
    print("Variance:", variance)

if __name__ == "__main__":
    main()

# Output : 
Mean: 3.6666666666666665
Variance: 1.5555555555555554

=== Code Execution Successful ===

# Results :
The mean and variance of arrivals of objects from feeder using probability distribution are calculated.

