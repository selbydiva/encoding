# Encoding

Encoding is a crucial step in data preprocessing that converts categorical data into numeric data. This process is important because many machine learning methods require numeric input to function properly. Categorical data can be divided into two groups: nominal categorical data and ordinal categorical data. Encoding techniques are used to handle both types. Here are the divisions and types of encoding:

<img width="1440" alt="en-1" src="https://github.com/user-attachments/assets/6ade7219-f016-4a3a-9e13-030b831d3174">

Here’s the data example that we will use. We can identify ‘marital_status’ as a nominal column and ‘performance’ as an ordinal column, as the categories in the ‘performance’ column can be ranked.

<img width="473" alt="Screenshot 2024-07-24 at 22 06 40" src="https://github.com/user-attachments/assets/57875a02-5300-44bd-aa9b-b78e496612dc">

# Ordinal Data

For ordinal data, we can rank category values based on their order. When converting ordinal categorical data to numeric data, we assign each category a numeric value according to its rank. We can use `LabelEncoder` from `sklearn.preprocessing` to perform this conversion. In the example below, there are four categories to convert. We know the order of these categories from highest to lowest: ‘excellent’, ‘good’, ‘poor’, and ‘bad’. The encoding result will be like this :

<img width="1440" alt="en-5" src="https://github.com/user-attachments/assets/ebe66ee2-12a4-4704-8d3e-879ed6f8b225">

Here's how we can apply encoding using python

<img width="588" alt="Screenshot 2024-07-24 at 22 14 58" src="https://github.com/user-attachments/assets/0db9aa5e-46c9-4c3d-b5f8-63598f7a23fa">

As we can see, the 'performance' column has four categories: 'excellent', 'good', 'poor', and 'bad'. `LabelEncoder` will automatically convert these categories to numeric values based on alphabetical order, resulting in the following mappings:

- 'bad': 0
- 'excellent': 1
- 'good': 2
- 'poor': 3
  
But that's not what we need. We want to order the 'performance' categories from the best to the worst, like this:

- 'excellent': 3
- 'good': 2
- 'poor': 1
- 'bad': 0

To achieve this, we can use `OrdinalEncoder` instead, because it allows us to define the order we want.

<img width="700" alt="Screenshot 2024-07-24 at 22 15 08" src="https://github.com/user-attachments/assets/70fd25ef-2324-4f75-b42e-0f617ec9217c">

In this code, we first define the order from lowest to highest and store it in 'categories'. We will use 'categories' as a parameter in OrdinalEncoder(). The output will then be in the desired format.

# Nominal Data

For nominal data, we cannot simply convert categories into ranked numerical values because nominal data does not have an inherent order. Forcing a ranking would introduce bias. Since nominal data lacks a natural order, we need to convert each category equally using binary (0 & 1) encoding. There are two methods to achieve this: One Hot Encoding and Dummy Encoding. Let’s use the previous dataset to convert the `marital_status` column. Below are the conversions of these two methods.

<img width="1438" alt="en-2" src="https://github.com/user-attachments/assets/f92a0b19-c846-4a84-b02e-6ee94049e183">

<img width="1436" alt="en-3" src="https://github.com/user-attachments/assets/6b2fb128-e8e3-4e0a-82cb-cbbb5d297a12">

One Hot Encoding and Dummy Encoding share the same concept, but Dummy Encoding can be more memory and computationally efficient due to the creation of fewer columns. The results of these two methods can be summarized as follows:

<img width="1054" alt="en-4" src="https://github.com/user-attachments/assets/29c28199-7781-4a98-a2f3-a6e6b1476ac9">

Let's try encoding the 'marital_status' column using Python.

**One Hot Encoding**

We can use OneHotEncoder from either `sklearn.preprocessing` or `category_encoders`. Here is a comparison of the results from both methods:

<img width="911" alt="Screenshot 2024-07-24 at 22 06 52" src="https://github.com/user-attachments/assets/6239fffe-9cdf-4911-9f5f-100483228559">

<img width="968" alt="Screenshot 2024-07-24 at 22 07 07" src="https://github.com/user-attachments/assets/a346d1d4-3797-4b6f-bcf9-91f8a4b08af8">

**Dummy Encoding**

<img width="946" alt="Screenshot 2024-07-24 at 22 25 53" src="https://github.com/user-attachments/assets/9077cd9b-6ac6-47d7-b57c-4aca809dfb36">







