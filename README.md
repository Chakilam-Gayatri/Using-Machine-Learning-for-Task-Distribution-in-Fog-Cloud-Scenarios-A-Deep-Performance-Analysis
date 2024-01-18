# Using-Machine-Learning-for-Task-Distribution-in-Fog-Cloud-Scenarios- Comparitive -Analysis
Source Paper : M. Pourkiani and M. Abedi, "Using Machine Learning for Task Distribution in Fog-Cloud Scenarios: A Deep Performance Analysis," 2021 International Conference on Information Networking (ICOIN), Jeju Island, Korea (South), 2021, pp. 445-450, doi: 10.1109/ICOIN50884.2021.9333929
https://ieeexplore.ieee.org/document/9333929

As a part of my Distributed Computing course in Master's , I perfomed the following performed a comparitive analysis on the above IEEE paper. 
The above uses MLTD to perform task distribution on fog servers. Look into the following scenarios to understand the various scenarios and task distribution across different fog servers.
Different Fog Servers with Similar Workloads (DFSW):

Given performance metrics:
Fog Server 1: {0.75: 1.43}
Fog Server 2: {0.75: 1.57}
Cloud Server: {0.75: 1.61}
Ideal Task Distribution: Each server handles tasks proportional to its performance capability. Given that a lower performance metric (e.g., 1.43) is better, Fog Server 1 is the most efficient. Therefore, it could handle a slightly higher workload compared to the others, while Fog Server 2 and the Cloud Server, having higher metrics, should handle a bit less to maintain efficiency.

Similar Fog Servers with Different Workloads that change randomly (SFDW):

Given performance metrics for each workload level (30%,
50%, 75%):
- Fog Server 1: {0.3: 1.43, 0.5: 1.57, 0.75: 1.61}
- Fog Server 2: {0.3: 1.43, 0.5: 1.57, 0.75: 1.61}
- Cloud Server: {0.3: 1.61, 0.5: 1.75, 0.75: 1.79}

Ideal Task Distribution: In this scenario, both Fog Servers are equally efficient at all workload levels, so they should be allocated an equal number of tasks. However, the Cloud Server shows less efficiency (higher performance metrics), especially as the workload increases. Therefore, it's ideal to allocate fewer tasks to the Cloud Server as workload increases, distributing more to the Fog Servers, especially at higher workload levels.

Similar Fog Servers with Similar Workloads (SFSW):

Given performance metrics:
Fog Server 1: {0.75: 1.43}
Fog Server 2: {0.75: 1.43}
Cloud Server: {0.75: 1.57}
Ideal Task Distribution: Since Fog Server 1 and Fog Server 2 have identical and better performance metrics than the Cloud Server, they should be allocated a similar and larger share of the tasks. The Cloud Server, being slightly less efficient, should handle fewer tasks to maintain overall system efficiency.

In summary, the ideal task distribution depends on the performance capability of each server. Efficient servers (with lower performance metrics) should handle more tasks, whereas less efficient servers should be allocated fewer tasks to optimize overall system performance.

When you look into the paper you notice that the MLTD alogrithm does not provide results that align with the ideal state. I have implemented the above scenarios uisng MLTD and as an enchancemt to the existing approach I also implemented the above scenarios using MLP Regressor, SVM and Decision Tree Regressors. If the task distribution to the fog servers happen efficiently it will aid in improving band width utilization, resource efficieny and latency.

Please run the above ipynb file to review the results.

PS:  MLP Regressor, SVM and Decision Tree Regressors outperformed MLTD. Amongst the three Decision Tree Regressor showed the best performnace.
