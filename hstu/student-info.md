classDiagram
    class Person {
        -person_id: string
        -name: string
        -email: string
        -phone: string
        +get_person_id(): string
        +get_name(): string
        +get_email(): string
        +get_phone(): string
    }

    class Student {
        -student_id: string
        +person_id: string
        -age: int
        -gender: string
        -advisor_id: string
        +get_student_id(): string
        +get_age(): int
        +get_gender(): string
        +get_advisor_id(): string
    }

    class Course {
        -course_id: string
        -name: string
        -credits: int
        -instructor_id: string
        +get_course_id(): string
        +get_name(): string
        +get_credits(): int
        +get_instructor_id(): string
    }

    class Grade {
        -student_id: string
        -course_id: string
        -grade: string
        +get_grade(): string
    }

    class Administrator {
        -admin_id: string
        +person_id: string
        -role: string
        +get_admin_id(): string
        +get_role(): string
    }

    class StudentInformationSystem {
        -students: list<Student>
        -courses: list<Course>
        -grades: list<Grade>
        -administrators: list<Administrator>
        +add_student(student: Student): void
        +add_course(course: Course): void
        +add_grade(grade: Grade): void
        +add_admin(admin: Administrator): void
    }

    StudentInformationSystem -- Student
    StudentInformationSystem -- Course
    StudentInformationSystem -- Grade
    StudentInformationSystem -- Administrator
    Student <-- Grade
    Course <-- Grade
    Administrator <-- Student
    Administrator <-- Course
