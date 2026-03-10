Student Performance:
This project analyses student performance data to understand how study habits and extracurricular activities relate to exam scores.

Question 1: Average exam score by hours studied
I filters the dataset to only incldue students who studied more than 10 hours and participated in extracurricular activites. 
I then grouped by hours_studied and the avg_exam_score before ordering from highest to lowest.

Limitations question 1:
This query does not tell you how the groups compare to students who don't participate in extracurricular activities. Not ideal for drawing conclusions.

Better approach:
Select hours_studied,
    extracurricular_activites,
    AVG(exam_score) As avg_exam_score
FROM student_performance
Where hours_studied >10
GROUP BY hours_studied, extracurricular_Activites
Order BY hours_studied DESC
LIMIT 5; 

Question 2: Average exam score by hours studied
Here I used a case statement to group students into bands.
Results are order by average exam score to show which range of hours studied performs best.

Question 3: Student Exam ranking (without skipping numbers)
Here I used DENSE_RANK so student with the same score get placed tied and the following student recieves second place rather than third.
The output contains attendance, hours studied, sleep hours and tutoring sessions to give further context.
The results are limited to the top 30 students. 

Tools:
SQL (PostgreSQL)

Data:
student_performance table

Author:
Don North
