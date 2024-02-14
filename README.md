# Birthday Greetings

## Project Description

The task is to implement a function that generates a list of colleagues to greet for the upcoming week based on their birthdays. You are provided with a list of dictionaries named `users`, where each dictionary must have the keys `name` and `birthday`. This structure represents a model of user information, including their names and birthdates. The `name` key contains a string with the user's name, and the `birthday` key contains a `datetime.date` object with the user's birthday.

**Example:**

```python
{"name": "Bill Gates", "birthday": datetime(1955, 10, 28).date()}
```

Your goal is to write a function called get_birthdays_per_week that takes the list of users as input and returns a dictionary of users to greet for each day in the next week.

The format of the dictionary returned by the get_birthdays_per_week function is as follows:

```python
{'Monday': ['Bill', 'Jan'], 'Wednesday': ['Kim']}
```

The keys of the dictionary represent the days of the week: "Monday", "Tuesday", "Wednesday", "Thursday", "Friday". The values are lists of users with birthdays for the week ahead, including the current day.

Note:

- If the script is run on a Wednesday, for instance, the keys "Wednesday", "Thursday", "Friday" will contain birthdays for the current week, while the keys "Monday", "Tuesday" will store birthdays for the next week. Birthdays falling on the weekend are included in the "Monday" key.
- The function should handle cases where a birthday has already occurred in the current year.
- The function should correctly account for weekends and shift them to Monday.
- The function should work correctly with an empty list of users.
- The function should handle situations where all birthdays have already passed in the current year.
