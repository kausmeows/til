## Validation vs Testint data

Not all data scientists rely on both validation data and testing data. To some degree, both datasets serve the same purpose: make sure the model works on real data.

However, there are some practical differences between validation data and testing data. If you opt to include a separate stage for validation data analysis, this dataset is typically labeled so the data scientist can collect metrics that they can use to better train the model. In this sense, validation data occurs as part of the model training process. Conversely, the model acts as a black box when you run testing data through it. Thus, validation data tunes the model, whereas testing data simply confirms that it works.

There is some semantic ambiguity between validation data and testing data. Some organizations call testing datasets “validation datasets.” Ultimately, if there are three datasets to tune and check ML algorithms, validation data typically helps tune the algorithm and testing data provides the final assessment.
