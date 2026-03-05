# Requirements Document

## Introduction

CareerSetu is an AI-powered Campus-to-Career Co-Pilot designed specifically for Tier-2 and Tier-3 engineering students in India. The platform addresses the critical gap in personalized career guidance by converting student profiles and real job descriptions into actionable, personalized learning roadmaps for Software Development Engineer (SDE), Data, and Cloud roles.

The solution tackles the widespread problem of students struggling with scattered YouTube content, generic roadmaps, and limited mentorship access, while considering India-specific constraints like language preferences and limited internet connectivity.

## Glossary

- **CareerSetu**: The AI-powered platform providing personalized career guidance
- **Student_Profile**: Complete profile including branch, skills, target role, time availability, and language preference
- **JD_Analyzer**: AI component that analyzes job descriptions to extract skill requirements
- **Roadmap_Generator**: AI system that creates personalized 30/60/90-day learning plans
- **RAG_System**: Retrieval-Augmented Generation system for curated learning resources
- **Progress_Tracker**: Component monitoring student advancement and updating roadmaps
- **Mock_Interview_Engine**: System providing practice interviews and coding questions
- **Multi_Language_Engine**: Component providing explanations in English and Indian languages
- **Resource_Curator**: System managing NPTEL, documentation, GitHub, and YouTube content
- **Skill_Gap_Analyzer**: AI component identifying gaps between current skills and job requirements

## Requirements

### Requirement 1: Student Profile Management

**User Story:** As a Tier-2/Tier-3 engineering student, I want to create and manage my comprehensive profile, so that I can receive personalized career guidance tailored to my background and goals.

#### Acceptance Criteria

1. WHEN a student registers, THE Student_Profile SHALL capture engineering branch, current skills, target role (SDE/Data/Cloud), daily time availability, and preferred language
2. WHEN a student updates their profile, THE Student_Profile SHALL validate all required fields and save changes immediately
3. WHEN profile data is incomplete, THE Student_Profile SHALL prevent roadmap generation and display specific missing information
4. THE Student_Profile SHALL support multiple Indian languages including Hindi, Tamil, Telugu, Bengali, and Marathi
5. WHEN a student selects a preferred language, THE Student_Profile SHALL store this preference for all future interactions

### Requirement 2: Job Description Analysis and Skill Gap Identification

**User Story:** As a student preparing for specific roles, I want the system to analyze real job descriptions and identify my skill gaps, so that I can focus on the most relevant skills for my target position.

#### Acceptance Criteria

1. WHEN a job description is provided, THE JD_Analyzer SHALL extract required technical skills, experience levels, and qualifications using AI
2. WHEN comparing student skills with job requirements, THE Skill_Gap_Analyzer SHALL identify specific skill gaps and proficiency levels needed
3. THE JD_Analyzer SHALL support job descriptions for SDE, Data Engineer, Data Scientist, Cloud Engineer, and DevOps roles
4. WHEN skill gaps are identified, THE Skill_Gap_Analyzer SHALL prioritize gaps based on job requirement importance and student's current level
5. THE JD_Analyzer SHALL handle job descriptions in both English and Hindi languages

### Requirement 3: Personalized Roadmap Generation

**User Story:** As a student with identified skill gaps, I want to receive a personalized 30/60/90-day learning roadmap, so that I can systematically prepare for my target role with clear daily and weekly goals.

#### Acceptance Criteria

1. WHEN skill gaps are identified, THE Roadmap_Generator SHALL create a structured 30/60/90-day learning plan with daily tasks and weekly milestones
2. WHEN generating roadmaps, THE Roadmap_Generator SHALL consider student's daily time availability and current skill level
3. THE Roadmap_Generator SHALL prioritize high-impact skills that appear in multiple job descriptions for the target role
4. WHEN creating daily tasks, THE Roadmap_Generator SHALL ensure each task is achievable within the student's specified daily time commitment
5. THE Roadmap_Generator SHALL include practical projects and hands-on exercises aligned with industry requirements

### Requirement 4: Curated Learning Resource Integration

**User Story:** As a student following a learning roadmap, I want access to high-quality, free learning resources curated specifically for Indian students, so that I can learn effectively without financial barriers.

#### Acceptance Criteria

1. THE Resource_Curator SHALL maintain a database of curated free resources from NPTEL, official documentation, GitHub repositories, and YouTube channels
2. WHEN recommending resources, THE RAG_System SHALL retrieve the most relevant content based on the current learning topic and student's proficiency level
3. THE Resource_Curator SHALL prioritize resources that provide explanations in Indian languages or have Indian context
4. WHEN internet connectivity is limited, THE RAG_System SHALL provide offline-capable resource recommendations and downloadable content
5. THE Resource_Curator SHALL validate resource quality and relevance through automated content analysis

### Requirement 5: Multi-Language Learning Support

**User Story:** As a student who prefers learning in my native language, I want explanations and guidance in Indian languages, so that I can understand complex technical concepts more effectively.

#### Acceptance Criteria

1. THE Multi_Language_Engine SHALL provide explanations for technical concepts in English, Hindi, Tamil, Telugu, Bengali, and Marathi
2. WHEN a student requests concept explanations, THE Multi_Language_Engine SHALL generate contextually appropriate explanations in the student's preferred language
3. THE Multi_Language_Engine SHALL maintain technical accuracy while adapting explanations to Indian cultural and educational contexts
4. WHEN translating technical terms, THE Multi_Language_Engine SHALL provide both translated terms and English equivalents for industry familiarity
5. THE Multi_Language_Engine SHALL support code comments and documentation translation for better comprehension

### Requirement 6: Mock Interview and Practice System

**User Story:** As a student preparing for technical interviews, I want to practice with mock interviews and coding questions relevant to my target role, so that I can build confidence and improve my interview performance.

#### Acceptance Criteria

1. THE Mock_Interview_Engine SHALL generate role-specific technical questions based on the student's target position and skill level
2. WHEN conducting mock interviews, THE Mock_Interview_Engine SHALL provide real-time feedback on answers and suggest improvements
3. THE Mock_Interview_Engine SHALL include coding problems with automated evaluation and hints for optimization
4. WHEN students complete practice sessions, THE Mock_Interview_Engine SHALL track performance metrics and identify weak areas
5. THE Mock_Interview_Engine SHALL support both English and preferred Indian language interactions during practice sessions

### Requirement 7: Progress Tracking and Adaptive Learning

**User Story:** As a student following a learning roadmap, I want the system to track my progress and adapt my plan based on my performance, so that I can stay on track and optimize my learning efficiency.

#### Acceptance Criteria

1. THE Progress_Tracker SHALL monitor daily task completion, quiz scores, and project submissions to assess learning progress
2. WHEN progress falls behind schedule, THE Progress_Tracker SHALL suggest plan adjustments and provide catch-up strategies
3. THE Progress_Tracker SHALL identify topics where students struggle and recommend additional resources or practice
4. WHEN students excel in certain areas, THE Progress_Tracker SHALL accelerate the roadmap and introduce advanced topics
5. THE Progress_Tracker SHALL provide weekly progress reports with achievements, challenges, and next week's focus areas

### Requirement 8: Mobile-First User Experience

**User Story:** As a student with limited access to computers, I want a mobile-friendly platform that works efficiently on my smartphone, so that I can learn and practice anywhere with minimal data usage.

#### Acceptance Criteria

1. THE CareerSetu SHALL provide a responsive web interface optimized for mobile devices with screen sizes from 320px to 768px
2. WHEN accessing on mobile networks, THE CareerSetu SHALL minimize data usage through content compression and efficient caching
3. THE CareerSetu SHALL support offline mode for previously accessed content and allow synchronization when connectivity is restored
4. WHEN using touch interfaces, THE CareerSetu SHALL provide intuitive navigation and touch-friendly interactive elements
5. THE CareerSetu SHALL load core functionality within 3 seconds on 3G networks

### Requirement 9: AWS Cloud Infrastructure Integration

**User Story:** As a system administrator, I want the platform to leverage AWS services for scalability, reliability, and cost-effectiveness, so that we can serve thousands of students efficiently within budget constraints.

#### Acceptance Criteria

1. THE CareerSetu SHALL use Amazon Bedrock for AI-powered job description analysis and roadmap generation
2. THE CareerSetu SHALL store user profiles and progress data in DynamoDB with automatic scaling based on demand
3. THE CareerSetu SHALL implement the RAG system using Amazon OpenSearch for efficient resource retrieval
4. THE CareerSetu SHALL use AWS Lambda for serverless compute to minimize costs during low-usage periods
5. THE CareerSetu SHALL store learning resources and user-generated content in S3 with CloudFront for global content delivery

### Requirement 10: Security and Privacy Protection

**User Story:** As a student sharing personal and academic information, I want my data to be secure and private, so that I can use the platform confidently without concerns about data misuse.

#### Acceptance Criteria

1. THE CareerSetu SHALL implement user authentication and authorization using Amazon Cognito with multi-factor authentication support
2. WHEN storing personal data, THE CareerSetu SHALL encrypt all sensitive information at rest and in transit
3. THE CareerSetu SHALL comply with Indian data protection regulations and provide clear privacy policies
4. WHEN users request data deletion, THE CareerSetu SHALL permanently remove all personal information within 30 days
5. THE CareerSetu SHALL implement role-based access control to ensure users can only access their own data and authorized resources