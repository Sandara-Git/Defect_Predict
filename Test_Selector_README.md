# Smart Test Selector:

Development team working on a large-scale web application that undergoes frequent updates and releases. 
The development process follows a continuous integration (CI) pipeline, where code changes are automatically built, tested, and deployed to various environments.
The test suite for the application includes a significant number of tests, ranging from unit tests to end-to-end tests, and the entire suite takes a substantial amount of time to run.

## Challenge:
The development team faces challenges with the testing phase of the CI pipeline. 
The growing codebase and extensive test suite result in longer build and test times. 
This delay hampers the rapid feedback loop essential for agile development practices. 
There is a need for a smart test selection mechanism that can efficiently choose a subset of tests to run based on the specific code changes made,
without compromising on the overall test coverage.

## Strategy for Smart Test Selection:
![Block_Diagram](https://github.com/Sandara-Git/Defect_Predict/assets/140485221/d271ed12-edb2-4f64-b2e1-7c4ce7993221)


### Relevant Data:
Some relevant data that can be collected from Git to identify code changes include:

A description of the change, often included in the commit message.

The commit number associated with the change.

The number of files and lines of code changed.

Differences before and after the change (via a function like "git diff").

References to issues or issues related to the change (via Git's issue tagging functionality).

Information about the author of the change, such as their name and email
The date and time the change was made

### Test case prioritization:
This technique involves assigning scores to test cases, reflecting their relevance to the introduced code modifications. Several methods can be employed for this purpose:

#### Semantic Similarity Measurement:

Utilize a measure of semantic similarity, such as the cosine of the angle between vectors representing the code change and each test case.
Assessing the semantic closeness helps quantify the relationship between the code modifications and individual test cases.

#### Distance Measurement:

Implement a distance measure, like the Levenshtein distance, to quantify the dissimilarity between the code change and each test case.
This method evaluates the proximity or dissimilarity between the code alteration and test case content.

#### Relevance Measure Based on Specific Terms:

Introduce a relevance measure considering specific terms, such as counting the number of common keywords between the code change and each test case.

Focusing on shared keywords helps capture the thematic alignment between the code modification and individual test cases.
Once relevance scores are assigned to each test case using one or a combination of these techniques, the next step is ordering the test cases based on their scores. The prioritization is established by presenting the highest-scoring test cases first, followed by those with lower scores. This systematic ordering ensures that test cases are prioritized according to their perceived connection with the code change, facilitating a more efficient testing strategy.

### Accessing test case repository
To access existing test cases written in Gherkin, the model could use a file read interface. This interface could be developed to allow the model to access and read the Gherkin files in the test case repository.

The interface could be developed using a programming language such as Python and could be integrated with the language model via an API. The interface could take as input the path of the Gherkin file.

### Ability to process user’s feedback to improve the algorithm 

Add a new class called "Feedback" that stores information about whether a test case selected by the model is correct or not. This class could have attributes such as the ID of the test case, the ID of the user who provided the feedback, and a boolean flag indicating whether the selected test case is correct or not.

Add a new function in the "MLModel" class called "processFeedback(feedback: Feedback)" that processes the feedback provided by the user. This function could update a counter internal to the model that keeps track of how many users have provided feedback for a specific test case and how many of them have rated it correct.

Modify the "predictRelatedTestCases(codeChange: ChangeInCode)" function to take user feedback into account when selecting test cases related to a specific change. For example, the model could give more weight to test cases that have been rated correct by a larger number of users.

Provide an interface for users to provide feedback, either through a web page or mobile app, where users can select a test case and provide feedback on whether or not that test case is correct.
Create a table in the database to store the feedback.

### Ability to suggest/create new test cases not included in the repository
The above approach could generate or suggest new scenarios that are not covered in the test case repository. 
This is because the model is capable of autonomous text generation, which means that it can generate new ideas and scenarios that are not present in the training dataset. However, it is important to note that the quality and relevance of these new scenarios will depend on the quality and quantity of training data that was used to train the model.

### Real-World Implementation:
Consider a scenario where a developer makes changes to a critical module related to user authentication. 
The smart test selector identifies this change and selects a subset of tests, including unit tests for the modified module, 
integration tests for modules interacting with authentication, and a subset of end-to-end tests covering critical user scenarios.
The smart test selector prevents unnecessary execution of unrelated tests, significantly reducing the overall test execution time. 
This allows the development team to receive faster feedback on the impact of their changes, facilitating quicker iterations and more efficient development cycles.
### Benefits:

Efficiency: Reduced test execution time, enabling quicker feedback to developers.

Coverage: Ensured test coverage for the modified code and related components.

Resource Optimization: Efficient utilization of CI/CD resources, allowing parallelization and scalability.

### Challenges and Considerations:

Dynamic Dependencies: Handling dynamic dependencies that may not be evident through static analysis alone.

Optimizing Speed: Balancing the need for comprehensive testing with the desire for quick feedback.

False Positives: Avoiding false positives by ensuring that the selected tests accurately represent the impact of code changes.

Maintaining Test Suites: Regularly updating and maintaining the test suite to reflect changes in the codebase.

In this real-world scenario, the smart test selector becomes an integral part of the CI/CD process, contributing to faster development cycles and improved overall software quality.
