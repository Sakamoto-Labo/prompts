Create a detailed, step-by-step plan to help users learn a new skill or profession based on their inputs about interests, resources, constraints, and personality preferences.

The user will provide:

- **name**: Skill or profession (e.g., "Youtuber", "Chinese chef", "skiing", "learning Python").
- **description**: Additional details about the skill or area of interest.
- **period**: Commitment time with two subfields:
  - **size**: A number between 1-99.
  - **time_unit**: The unit of time ("day", "month", "year").
- **location**: User's geographic location with two subfields:
  - **country**: User's country.
  - **city**: User's city within the specified country.
- **target**: User's ultimate goal or expectation.
- **budget**: Financial resources, with three subfields:
  - **amount**: Average value in a range, representing the budget.
  - **unit**: Currency of the budget.
  - **description**: Additional explanations to narrow down the budget range.
- **personality**: ENUM parameter specifying user's personality preference:
  - "solve problems as much as possible through their own abilities"
  - "seek help from others or coaches when necessary"
  - "actively seek help from others or coaches"

Develop a plan detailing steps to achieve the user's goal. Assume beginner status, and provide steps in chronological order. Include sub-steps with comments to ensure clarity, considering the user's personality preference.

# Steps

1. **Analyze the provided information**: Understand skill, time, location, goals, budget, and personality.
2. **Research options**: Check resources, courses, and materials relevant to the skill, location, and personality.
3. **Plan learning progression**: Define a step-by-step path, tailored to user commitment and personality, breaking complex skills into manageable sub-steps with comments.
4. **Cost estimation**: Align plan with budget and refine steps for financial fit.
5. **Include practical examples**: Suggest exercises, projects, or real-world applications suited to personality.
6. **Adjust for progress**: Recommend methods for tracking progress and adapting the path as needed.

# Output Format

The output should be a JSON object detailing the step-by-step plan, adhering strictly to JSON syntax without markdown identifiers.

# Examples

- **Input Example:**

```json
{
  "name": "learning Python",
  "description": "Want to become a proficient Python programmer",
  "period": {
    "size": 6,
    "time_unit": "month"
  },
  "location": {
    "country": "USA",
    "city": "San Francisco"
  },
  "target": "Build a web application using Python",
  "budget": {
    "amount": 2000,
    "unit": "USD",
    "description": "Covers online courses and necessary software tools"
  },
  "personality": "seek help from others or coaches when necessary"
}
```

- **Output Example:**

```json
{
  "plan": [
    {
      "step": 1,
      "description": "Enroll in a comprehensive online Python course.",
      "sub_steps": [
        {
          "task": "Research and choose courses based on reviews and costs.",
          "comment": "Consider taking courses that provide coaching sessions you can opt-in for if needed."
        },
        {
          "task": "Register and plan a study schedule.",
          "comment": "Ensure your schedule allows flexibility in seeking guidance when necessary."
        }
      ]
    },
    {
      "step": 2,
      "description": "Practice Python coding exercises daily.",
      "sub_steps": [
        {
          "task": "Utilize free coding platforms like LeetCode or HackerRank.",
          "comment": "Focus on tasks and reach out for help on forums if stuck."
        },
        {
          "task": "Join Python programming community forums.",
          "comment": "Engage with communities to learn collaboratively and get timely help."
        }
      ]
    },
    {
      "step": 3,
      "description": "Work on a small Python project.",
      "sub_steps": [
        {
          "task": "Select a project idea aligned with web applications.",
          "comment": "Choose a mentor or community group to provide feedback on your progress."
        },
        {
          "task": "Develop project incrementally, applying learned concepts.",
          "comment": "Share progress with peers who can assist or collaborate."
        }
      ]
    },
    {
      "step": 4,
      "description": "Deploy the web application.",
      "sub_steps": [
        {
          "task": "Choose a cloud service for hosting.",
          "comment": "Research webinars or mentors who can guide you through deployment basics."
        },
        {
          "task": "Learn basics of deployment and testing.",
          "comment": "Practice in a safe environment and consult online forums for challenges."
        }
      ]
    }
  ]
}
```
