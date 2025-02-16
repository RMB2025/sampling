# ASSIGNMENT: Sampling and Reproducibility in Python

Read the blog post [Contact tracing can give a biased sample of COVID-19 cases](https://andrewwhitby.com/2020/11/24/contact-tracing-biased/) by Andrew Whitby to understand the context and motivation behind the simulation model we will be examining.

Examine the code in `whitby_covid_tracing.py`. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times

# Author: Roslyn Bryan

```
Please write your explanation here...
The def simulate_event(m) function creates a population of individuals attending weddings and brunches. This population is originally uninfected, but Attack_Rate is used to randomly infect 10 percent of the population. 

The sampling frame population is the proportion of the population randomly selected to be infected. The function then performs primary and secondary contact tracing on the sample and calculates the proportion of infections and the proportions of traced cases that are attributed to weddings.

The total population is 1000 people, 200 of whom are wedding attendees, and 800 of whom make up the general population.

The repetition of 1000 creates a graph that shows the proportion of cases traced to weddings as being very similar to the graph of infections from weddings, showing a close relationship between the two. However, the graphs in the blog suggests that the two graphs are not closely related. The graph showing the observed proportion of infections resulting from weddings is much wider and has a mean that is much greater than the mean of the True proportion graph.

After changing the number of repetitions in the simulation to 100, I ran the script more than multiple times, and got different results each time. At no time did I get graphs that looked like the graphs in the blog.

To make the code reproducible, I added a constant random seed. 

Inside the simulate_event function, I added np.random.seed(SEED + m) to set the seed for the random number generator. 

Setting a seed for the random number generator ensured the same sequences of random numbers were generated each time the code was run. This made it possible for the same infected people and same tracing decisions to used for each run.

The changes made the script file reproducible so that the graphs were the same every time the script was run, making the results more reliable.


```


## Criteria

|Criteria|Complete|Incomplete|
|--------|----|----|
|Altercation of the code|The code changes made, made it reproducible.|The code is still not reproducible.|
|Description of changes|The author explained the reasonings for the changes made well.|The author did not explain the reasonings for the changes made well.|

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 16/02/2025`
* The branch name for your repo should be: `assignment-1`
* What to submit for this assignment:
    * This markdown file (a1_sampling_and_reproducibility.md) should be populated.
    * The `whitby_covid_tracing.py` should be changed.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `assignment-1`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
