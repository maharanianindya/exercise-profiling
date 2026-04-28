Performance Testing Results

1. /all-student
<img width="2940" height="1912" alt="image" src="https://github.com/user-attachments/assets/f89a411e-e725-4981-a5e5-fe2592b50e14" />

2. /all-student-name
<img width="2940" height="1912" alt="image" src="https://github.com/user-attachments/assets/399d0692-ad86-4c01-b2a4-e0627d5ccd46" />

3. /highest-gpa
<img width="2940" height="1912" alt="image" src="https://github.com/user-attachments/assets/00ebf741-0288-47ed-a07f-5d2e45256d97" />

CLI Results

1. /all-student
<img width="959" height="196" alt="test_result_log_1" src="https://github.com/user-attachments/assets/ffcbf711-0755-4e12-8e36-7eba0acdaf54" />

2. /all-student-name
<img width="2208" height="364" alt="image" src="https://github.com/user-attachments/assets/c774cfb4-adae-413f-9ec6-3a725df6526f" />

3. /highest-gpa
<img width="2168" height="370" alt="image" src="https://github.com/user-attachments/assets/abf0727d-c96f-4428-a906-4779b1380826" />

After optimization, the response times for the endpoints decreased compared to the initial measurements. For example, the /highest-gpa endpoint showed a noticeable improvement, with the average elapsed time reduced by more than 20%. This indicates that the system is able to handle requests more efficiently after the refactoring. The improvement was mainly achieved by simplifying the service logic and moving the data processing to the database layer. Instead of processing all the data in the application, the system now retrieves only the required result directly from the database, which reduces unnecessary computation. Overall, the optimization successfully improved the application’s performance by reducing response time and making the system more efficient.

Reflection
1. JMeter measures how the application performs from the outside, like response time under load. IntelliJ Profiler looks inside the application and shows which methods or parts of the code are slow. So JMeter tells you what is slow, while the profiler tells you why.
2. Profiling shows which methods consume the most time or resources. This makes it easier to pinpoint inefficient code, like repeated database calls or unnecessary loops, instead of guessing.
3. Yes, it’s very helpful. It clearly shows which parts of the code are taking the most time, so it makes debugging performance issues much faster and more focused.
4. One challenge is inconsistent results, especially when response times fluctuate. Another is understanding the profiler output. I handled this by running tests multiple times and focusing on consistent patterns rather than one-off results.
5. It helps visualize performance issues, identify bottlenecks quickly, and understand how the application behaves internally. This makes optimization more targeted and effective.
6. I compare both results and try to understand the difference. JMeter reflects real-world performance, while the profiler focuses on code behavior. I rely on both and look for patterns instead of exact numbers.
7. I reduced unnecessary database calls, especially fixing the N+1 query problem in /all-student, and moved some logic to the database for /highest-gpa. After that, I tested the endpoints again to make sure the results were correct and performance improved.
