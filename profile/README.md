# [KinesteX AI Fitness SDK](https://kinestex.com)
## INTEGRATE AI TRAINER IN YOUR APP IN MINUTES
### Easily transform your platform with our SDK: white-labeled workouts with precise motion tracking and real-time feedback tailored for accuracy and engagement

Jump to an example in your programming language:
|[**Flutter**](https://github.com/KinesteX/KinesteX-SDK-Flutter) |[**React Native**](https://github.com/KinesteX/KinesteX-SDK-ReactNative) |[**Swift**](https://github.com/KinesteX/KinesteX-SDK-Swift) | [**Kotlin**](https://github.com/KinesteX/KinesteX-SDK-Kotlin)| [**HTML & JS**](https://github.com/KinesteX/KinesteX-SDK-HTML-JS) | [**React Progressive Web App**](https://github.com/KinesteX/KinesteX-SDK-PWA) |
---------|-------------|------------|------------|---------------------------|--------------|

https://github.com/V-m1r/KinesteX-B2B-AI-Fitness-and-Physio/assets/62508191/ac4817ca-9257-402d-81db-74e95060b153


KinesteX revolutionizes fitness and health industries with our cutting-edge embeddable SDK. Using device's camera, our AI precisely analyzes human movements in real-time, providing instant, expert-level guidance tailored to the individual's form. Our movements recognition models consistently exceed 90% accuracy, enhancing user's workout experience, and helping them achieve their fitness goals faster. Our AI Fitness Trainer is available for your programming language, we have created light-weight packages for Flutter, SwiftUI, React Native, Kotlin, PWA. In case your programming language is missing, please contact us and we will create a custom example for you and guide you through the process!

## Available data types
 
    
| Type          | Data  |          Description     |
|----------------------|----------------------------|---------------------------------------------------------|
| `kinestex_launched`  | Format: `dd mm yyyy hours:minutes:seconds` | When a user has launched KinesteX 
| `exit_kinestex`     | Format: `date: dd mm yyyy hours:minutes:seconds`, `time_spent: number` | Logs when a user clicks on exit button, requesting dismissal of KinesteX and sending how much time a user has spent totally in seconds since launch   |
| `plan_unlocked`    | Format: `title: String, date: date and time` | Logs when a workout plan is unlocked by a user    |
| `workout_opened`      | Format: `title: String, date: date and time` | Logs when a workout is opened by a user  |
| `workout_started`   |  Format: `title: String, date: date and time`| Logs when a workout is started.  |
| `error_occurred`    | Format:  `data: string`  |  Logs when a significant error has occurred. For example, a user has not granted access to the camera  |
| `exercise_completed`      | Format: `time_spent: number`,  `repeats: number`, `calories: number`,  `exercise: string`, `mistakes: [string: number]`  |  Logs everytime a user finishes an exercise |
| `total_active_seconds` | Format: `number`   |   Logs every `5 seconds` and counts the number of active seconds a user has spent working out. This value is not sent when a user leaves camera tracking area  |
| `left_camera_frame` | Format: `number`  |  Indicates that a user has left the camera frame. The data sent is the current number of `total_active_seconds` |
| `returned_camera_frame` | Format: `number`  |  Indicates that a user has returned to the camera frame. The data sent is the current number of `total_active_seconds` |
| `workout_overview`    | Format:  `workout: string`,`total_time_spent: number`,  `total_repeats: number`, `total_calories: number`,  `percentage_completed: number`,  `total_mistakes: number`  |  Logged when a user finishes the workout with a complete short summary of the workout  |
| `exercise_overview`    | Format:  `[exercise_completed]` |  Returns a log of all exercises and their data (exercise_completed data is defined 5 lines above) |
| `workout_completed`    | Format:  `workout: string`, `date: dd mm yyyy hours:minutes:seconds`  |  Logs when a user finishes the workout and exits the workout overview |
| `active_days` (Coming soon)   | Format:  `number`  |  Represents a number of days a user has been opening KinesteX |
| `total_workouts` (Coming soon)  | Format:  `number`  |  Represents a number of workouts a user has done since start of using KinesteX|
| `workout_efficiency` (Coming soon)  | Format:  `number`  |  Represents the level of intensivity a person has done the workout with. An average level of workout efficiency is 0.5, which represents an average time a person should complete the workout for at least 80% within a specific timeframe. For example, if on average people complete workout X in 15 minutes, but a person Y has completed the workout in 12 minutes, they will have a higher `workout_efficiency` number |
------------------


### To get demo access and your api key, please fill out a form [on our website](https://kinestex.com#contact-form)

Or, alternatively: 
- Send us an email to [support@kinestex.com](mailto:support@kinestex.com)
- In the email subject write: B2B Demo Access
- In the email body include any supporting details (company / project name, site, programming language your project is written in, etc.)

-------

# Once you have contacted us, you may
Refer to packages based on your programming language:
|[**Flutter**](https://github.com/KinesteX/KinesteX-SDK-Flutter) |[**React Native**](https://github.com/KinesteX/KinesteX-SDK-ReactNative) |[**Swift**](https://github.com/KinesteX/KinesteX-SDK-Swift) | [**Kotlin**](https://github.com/KinesteX/KinesteX-SDK-Kotlin)| [**HTML & JS**](https://github.com/KinesteX/KinesteX-SDK-HTML-JS) | [**React Progressive Web App**](https://github.com/KinesteX/KinesteX-SDK-PWA) |
---------|-------------|------------|------------|---------------------------|--------------|

For any questions, please contact: support@kinestex.com
