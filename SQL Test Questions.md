
1.   SELECT AVG(grade) AS average_grade
FROM Enrollments;

2. SELECT Students.name, Courses.course_name
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;

3. SELECT grade_level, COUNT(student_id) AS student_count
FROM Students
GROUP BY grade_level;

4. SELECT course_id, MAX(grade) AS max_grade
FROM Enrollments
GROUP BY course_id;

5. SELECT AVG(Enrollments.grade) AS avg_grade_level_3
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
WHERE Students.grade_level = 3;

6. SELECT Students.name, Courses.course_name, Courses.credits
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;

7. SELECT Courses.course_name
FROM Enrollments
JOIN Courses ON Enrollments.course_id = Courses.course_id
GROUP BY Courses.course_name
HAVING AVG(Enrollments.grade) > 3.0;

8. SELECT Students.name
FROM Students
WHERE Students.student_id NOT IN (
    SELECT student_id
    FROM Enrollments
    WHERE grade = 4.0
);

9. SELECT Students.name
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
GROUP BY Students.name
HAVING AVG(Enrollments.grade) > (
    SELECT AVG(grade)
    FROM Enrollments
);

10. SELECT Students.name, COUNT(Enrollments.course_id) AS total_courses, AVG(Enrollments.grade) AS avg_grade
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
GROUP BY Students.name;


