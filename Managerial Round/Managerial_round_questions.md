### 1. Tell me about yourself

Hi, Greetings!

My name is [your name]. Currently I'm working as a Data engineer at [company name]. I have around 3 years of experience as a Data Engineer.

In these 3 years I have worked on different projects but mainly I worked on migrating on-premises ETL jobs to Azure Cloud, where we used Azure Data Factory to orchestrate data pipelines and Databricks and SQL for data transformations.

Currently, I part of a project called [project name], where we are developing an end-to-end ETL pipeline for processing data from over 30 diverse sources to meet regulatory and business requirements.

I’m certified as a Databricks Data Engineer Associate and in also certified in Azure  cloud Fundamentals and Data fundamentals.

### 2. Give an overview of projects/Explain your project
My project is basically of a banking and financial domain.

The goal of the project was to create a data pipelines to meet regulatory and business requirements, including monitoring activities like Anti-Money Laundering(AML).

We are following this medallion architecture. 

**Ingestion:**
- Where we are getting a data into ADLS from over 30 diverse sources. which we are calling a SRZ zone which a single source of truth acorss the enterprise.

**Processing:**
- We are processing the data on incremental basis using azure databricks. so the data parquet files in delta tables in adls which is our bronze layer.
- then we are reading the data using pyspark and applying business logic and we are loading into the delta tables in adls.

**Output:**
- Finally,  we are creating a csv files out of these tables and delivering to the business teams, where they are generating reports out of it for Analysis.

### 3. How much data you deal with on a daily basis
- We are processing the data on incremental basis around 5-7 GB of data daily.

### 4. what is the size of your cluster 
- We are using databricks runtime version 15.2
- In Dev, 128 GB 32 cores and 1-10 min max workers
- Each node in our cluster is configured with 128GB RAM and 16 CPU cores
- In Prod, 256 GB, 64 cores and 1-10 min max workers

### 5. what is your role in your big data project/data engineering projects
In my data engineering projects, I primarily serve as a Data Engineer. 

**My key responsibilities include:**
- Designing and Implementing Data Pipelines:

- Data Processing and Transformation:
  - I work with PySpark in Azure Databricks to process large datasets, apply business logic, and store processed data in Delta tables for optimized performance and query speed.

- Collaboration with Stakeholders:
  - I collaborate with business analysts to understand requirements and ensure the data pipeline delivers accurate, clean, and timely data for analysis.

- Automation and Monitoring:
  - I automate the pipeline schedules using Azure Data Factory, monitor performance, and troubleshoot any issues that arise in the data flow


### 6. Whats the most challenging thing that you faced in your project & how you overcome that.?

**Partial Execution/incomplete data processing:**

One of the most challenging issues I faced in the project was dealing with incomplete data during the production process. We were using event-based triggers, so the ETL process would start as soon as the file arrived. However, if there was an issue on the ingestion side, we would end up processing incomplete data for that day. 

This meant we had to restore tables to their previous version and reprocess the data once the ingestion team confirmed the data was complete.
To overcome this challenge, We implemented a pre-processing script that validated the data for each partition. The script checked if the data volume matched the expected amount.
If the data was incomplete, the execution would stop, preventing the processing of incorrect data.

This approach significantly reduced rework and ensured that only complete data was processed.

**Schelding the pipelines Only on Business Days:**

A significant challenge I faced was scheduling the pipelines to run only on business days, excluding holidays. We were using an orchestration framework for scheduling, but it didn’t have native support for excluding business holidays. We needed a way to ensure data was processed only on business days, not during holidays.

To solve this, we created a CSV file containing a list of holiday dates. Before triggering the pipelines, I developed a script that checked the current date against the holiday list. If the day was a holiday, the script would stop the pipeline execution and send an email notification. If it was a business day, the pipeline would proceed as usual.

This solution ensured that data was processed only on valid business days and helped maintain smooth operations during holiday periods.

### 7. How do you prioritize tasks and manage deadlines in a fast-paced environment, especially when working on multiple data projects simultaneously?

I prioritize tasks based on their urgency, impact, and alignment with business goals.

**Assessing Urgency and Business Impact:**
- I prioritize tasks based on their urgency and business impact, focusing on those that are critical or blocking others.

**Breaking Down Tasks and Setting Milestones:**
- I break down larger tasks into smaller, manageable milestones with clear deadlines.

**Delegation and Collaboration:**
- I delegate tasks according to team members’ strengths and ensure regular communication through check-ins.

**Using Tools for Tracking and Communication:**
- I use project management tools like Jira or Trello to track progress and maintain alignment.

**Flexibility and Adaptability:**
- I stay flexible and adapt quickly to shifting priorities or deadlines, ensuring timely delivery without compromising quality.

### 8. How do you handle conflicts within the team, especially when it comes to disagreements about data approaches or methodologies? Can you share an example of how you resolved such a situation?
- When handling conflicts within the team, especially regarding data approaches or methodologies, I focus on open communication and collaboration. 
- First, I listen to all perspectives to fully understand the reasoning behind different approaches. Then, I facilitate a discussion where team members can explain their points of view and provide data or examples to support their positions.
- If needed, I suggest we experiment with a small-scale prototype to test different approaches and compare results objectively. This helps us make data-driven decisions rather than relying solely on opinions.
- For example, in one of my previous projects, there was a disagreement between team members about whether to use Spark SQL or PySpark for data transformations. I encouraged both sides to present their reasoning and then proposed a small pilot project to compare the performance and scalability of both. After testing, we chose the best approach based on the actual results, which helped resolve the conflict and move forward

### 9. What is your Weakness and How do you overcome your weakness?

One of my weaknesses is that I can sometimes be overly `detail-oriented`, which might slow me down when I’m reviewing my work or validating data.
While I believe attention to detail is critical in data engineering, I’ve learned to balance this by setting time limits for tasks and focusing on delivering within deadlines.

Also one of my weaknesses is that unfinished work annoys me, and I tend to overthink it. I also find it hard to say 'no' when others ask for help, which sometimes affects my workload. Additionally, I prefer to focus on one task at a time, which can be challenging in multitasking environments. However, I’m aware of these areas and actively working to improve them.

### 10. what is your strength?

My strength is that I am adaptable to new working environments and self-motivated, flexible, and self-disciplined. I'm constantly eager to meet new people and develop new skills. I always give it my all to complete my task on time.

Additionally, my attention to detail ensures data accuracy, and my collaborative nature helps me work effectively with teams to achieve goals."

### 11. What do you want to achieve professionally in the long run?
In the long run, I want to grow as a data engineering expert, contributing to impactful projects that solve real-world problems.

I aim to take on leadership roles where I can mentor teams, drive innovation, and optimize data solutions to support business decisions. 

Ultimately, I want to keep learning and stay updated with emerging technologies to remain a valuable asset in the field.

#### 12. What does Success mean to you?
To me, success means consistently achieving my goals while making a positive impact.

It’s about growing both personally and professionally, contributing value to my team and organization, and continuously improving my skills. 

Success is not just about outcomes but also the learning and growth along the way.

### 13. What kind of work atmosphere would you prefer?
I prefer a collaborative and supportive work atmosphere where team members share knowledge and work together toward common goals. 

An environment that encourages learning, open communication, and innovation motivates me to perform at my best. I also value clear expectations and opportunities for growth.

### 14. What is your ideal job? 
My ideal job is one where I can leverage my technical skills in data engineering to solve complex problems and create efficient, scalable solutions. 

It would involve working on challenging projects, learning new technologies, and contributing to meaningful business outcomes. I also value a role that offers opportunities for growth, collaboration, and innovation.

### 15. How can you help the company?
I can help the company by bringing my expertise in data engineering to design and optimize efficient data pipelines that improve data accessibility, quality, and processing speed.

With my experience in working with tools like Azure Databricks and PySpark, I can help streamline workflows, reduce processing time, and ensure the delivery of actionable insights.

Additionally, I’m adaptable and proactive, always looking for ways to improve processes, collaborate with teams, and drive business value through data.

### What are your salary expectations?
Based on my experience, skills, and market research, I am looking for a salary in the range of 10-12 LPA. 

However, I am open to discussing the compensation package based on the overall opportunity, growth potential, and other benefits that come with the role.

### What do you like in Wipro?
What I admire about Wipro is its strong reputation for innovation, commitment to technology, and global presence.

The company’s focus on continuous learning and development is particularly appealing to me, as I value environments that encourage growth and skill enhancement. Throught my 3 years in wipro I was part of the upskilling and training programs conducted my wipro. where we can have mentors for skills we want to learn and also the sposership for any certifications.

Additionally, I respect Wipro’s customer-centric approach and its focus on building long-term relationships, which aligns with my values of delivering impactful and quality work.

### What do you don’t like in Wipro?
I don't have any specific dislikes about Wipro, but one thing I would be mindful of is the large-scale nature of the organization, which can sometimes lead to slower decision-making processes due to multiple layers of hierarchy.

However, I also recognize that this can be part of working in a large, established company, and I would focus on navigating those challenges effectively by working collaboratively and being adaptable.

One challenge I’ve observed in large companies is the potential for silos between teams, which can affect communication. However, I believe in the importance of cross-team collaboration and would make an effort to break down any barriers to ensure alignment and shared goals.

#### Let’s say you got an offer for 7 LPA at Infosys and some other organisations offer you 10 LPA. Which company you will go for it.
While salary is an important factor, it’s not the only consideration for me. I value the opportunity for growth, learning, and the kind of work I’ll be doing.

Infosys offers an environment where I can grow professionally, work on challenging projects, and collaborate with a great team, I would be inclined to choose that, even with a slightly lower salary.

Ultimately, I want to be in a place where I can develop my skills, contribute meaningfully, and align with the company’s culture and values. That said, I’d carefully weigh all aspects, including work-life balance, career development opportunities, and the kind of projects I'll be working on.


### Have you got any questions for us?
- Can you tell me more about the team I’ll be working with and how they collaborate?
- What opportunities for professional development and growth does the company offer?

