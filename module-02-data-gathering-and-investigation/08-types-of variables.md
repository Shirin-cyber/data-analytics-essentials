# Types of Variables

In the previous section, we learned that a variable is a characteristic or feature recorded in a dataset. But not all variables contain the same kind of information.

For example, a dataset might contain someone's age, their favourite colour, their exam marks, or their level of satisfaction with a service. These are different kinds of information, so we need to understand how variables are classified.

The two main types are **categorical variables** and **numerical variables**.

## 1. Categorical variables

Categorical variables describe groups, labels, or categories rather than measuring a numerical quantity.

For example:
- Eye colour: brown, blue, green
- Course: BCA, BCom, BA
- Satisfaction level: dissatisfied, neutral, satisfied

Categorical variables can be divided into two types.

### Nominal variables

A **nominal variable** contains categories that have no natural order.

For example, eye colour can be brown, blue, or green. There is no correct ranking that places one of these categories above the others.

Other examples include blood group, country, and type of vehicle.

### Ordinal variables

An **ordinal variable** contains categories that follow a meaningful order.

For example, satisfaction levels might be arranged as:

`Dissatisfied → Neutral → Satisfied`

The categories have an order, but the difference between each level cannot automatically be treated as equal.

Other examples include education levels and customer ratings such as poor, average, good, and excellent.

## 2. Numerical variables

Numerical variables represent quantities that can be expressed as numbers.

Examples include age, height, temperature, salary, and the number of students in a class.

Numerical variables can be divided into two types.

### Discrete variables

A **discrete variable** takes separate, countable values. These often come from counting something.

For example:
- Number of students in a classroom
- Number of books on a shelf
- Number of computers in a lab

You can have 20 students or 21 students, but you cannot have 20.5 students in a simple headcount.

### Continuous variables

A **continuous variable** can take any value within a range, depending on the precision of the measurement.

For example:
- Height: 165.5 cm
- Weight: 52.8 kg
- Time taken to complete a task: 12.6 seconds

These measurements can include decimal values, and they can be measured at different levels of precision.

## Quick comparison

| Variable type | Meaning | Example |
|---|---|---|
| Nominal | Categories with no natural order | Eye colour |
| Ordinal | Categories with a meaningful order | Satisfaction level |
| Discrete | Countable numerical values | Number of students |
| Continuous | Measurable numerical values across a range | Height |

## One important thing to remember

A number doesn't always mean that a variable is numerical in the analytical sense.

For example, a student ID might be `101`, `102`, or `103`. Although these values look like numbers, they identify students rather than measure a quantity. Student ID is therefore a categorical identifier, not a numerical measurement.

Understanding the type of each variable helps us decide how to analyse the data and which visualizations are appropriate.

## My main takeaway

Categorical variables describe categories, while numerical variables represent quantities. Nominal and ordinal variables are categorical; discrete and continuous variables are numerical. Identifying the variable type is an important step before choosing how to analyse or visualize a dataset.
