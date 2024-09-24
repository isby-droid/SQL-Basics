
1.   SELECT AVG(grade) AS average_grade
FROM Enrollments;

2. SELECT s.name, c.course_name
FROM Enrollments e
JOIN Students s ON e.student_id = s.student_id
JOIN Courses c ON e.course_id = c.course_id;

3. SELECT grade_level, COUNT(*) AS student_count
FROM Students
GROUP BY grade_level;

4. SELECT c.course_name, MAX(e.grade) AS max_grade
FROM Enrollments e
JOIN Courses c ON e.course_id = c.course_id
GROUP BY c.course_name;

5. SELECT AVG(e.grade) AS average_grade_level_3
FROM Enrollments e
JOIN Students s ON e.student_id = s.student_id
WHERE s.grade_level = 3;

6. SELECT s.name, c.course_name, c.credits
FROM Enrollments e
JOIN Students s ON e.student_id = s.student_id
JOIN Courses c ON e.course_id = c.course_id;

7. SELECT c.course_name, AVG(e.grade) AS average_grade
FROM Enrollments e
JOIN Courses c ON e.course_id = c.course_id
GROUP BY c.course_name
HAVING AVG(e.grade) > 3.0;


8. SELECT s.name
FROM Students s
WHERE s.student_id NOT IN (
    SELECT DISTINCT e.student_id
    FROM Enrollments e
    WHERE e.grade = 4.0
);

9. SELECT s.name
FROM Students s
JOIN (
    SELECT student_id, AVG(grade) AS avg_student_grade
    FROM Enrollments
    GROUP BY student_id
) student_avg ON s.student_id = student_avg.student_id
WHERE student_avg.avg_student_grade > (
    SELECT AVG(grade)
    FROM Enrollments
);


10. SELECT s.name, COUNT(e.course_id) AS total_courses, AVG(e.grade) AS average_grade
FROM Enrollments e
JOIN Students s ON e.student_id = s.student_id
GROUP BY s.name;



