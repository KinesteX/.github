# [Precise Motion Tracking and Analysis SDK](https://kinestex.com)
## Stay Ahead with KinesteX AI Motion Tracking.
### White-labeled motion tracking SDK with ready-made or custom AI experiences, boosting your app’s user engagement and revenue

Jump to an example in your programming language:
|[**Flutter**](https://github.com/KinesteX/KinesteX-SDK-Flutter) |[**React Native**](https://github.com/KinesteX/KinesteX-SDK-ReactNative) |[**Swift**](https://github.com/KinesteX/KinesteX-Swift-Demo) | [**Kotlin**](https://github.com/KinesteX/KinesteX-SDK-Kotlin)| [**HTML & JS**](https://github.com/KinesteX/KinesteX-SDK-HTML-JS) | [**React Progressive Web App**](https://github.com/KinesteX/KinesteX-SDK-PWA) |
---------|-------------|------------|------------|---------------------------|--------------|

https://github.com/V-m1r/KinesteX-B2B-AI-Fitness-and-Physio/assets/62508191/ac4817ca-9257-402d-81db-74e95060b153


KinesteX offers a powerful motion tracking SDK that seamlessly integrates into your platform. 
Choose between ready-made workouts, plans, challenges, AI assessments, or create custom experiences with our advanced motion tracking.

Our white-label solution supports any camera-enabled device across Android, iOS, web, and gaming platforms, with SDKs for React Native, Flutter, Kotlin, Swift, Java, PWA, and JavaScript for quick integration.

KinesteX’s real-time AI motion tracking boosts engagement, retention, and revenue while providing valuable data insights to create personalized, growth-driving experiences

# PostMessage Events Documentation

PostMessage events are sent to parent windows/webviews for integration with native apps and external systems, they work in real-time, safely, and can even send data back to you offline!

## Application Lifecycle

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `kinestex_launched` | `data: string` (format: "dd mm yyyy hh:mm:ss") | When KinesteX application is launched |
| `kinestex_loaded` | `date: string` (ISO format) | When KinesteX is fully loaded and ready |
| `exit_kinestex` | `date: Date`, `time_spent: string` (format: "hh:mm:ss") | User exits KinesteX with total time spent |
| `main_page_opened` | `date: string` (ISO format) | Main/home page is opened |

## Workout Management

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `workout_opened` | `title: string`, `id: string`, `date: string` (format: "dd mm yyyy hh:mm:ss") | Workout details page opened |
| `workout_started` | `id: string`, `date: string` (format: "dd mm yyyy hh:mm:ss") | Workout session started |
| `workout_started` (alt) | `workoutId: string` | Alternative workout start event |
| `workout_completed` | `workout: string`, `date: string` (format: "dd mm yyyy hh:mm:ss") | Workout finished and user exits overview |
| `workout_overview` | `data: object` - see below | Complete workout summary statistics |

### Workout Overview Data Structure
```typescript
{
  workout: string,              // Workout name
  total_time_spent: number,     // Total seconds
  total_repeats: number,        // Total reps completed
  total_calories: string,       // Calories burned (decimal)
  percentage_completed: string, // Completion percentage (decimal)
  total_mistakes: number,       // Total mistakes made
  total_max_reps: number,       // Maximum possible reps
  total_accuracy_score: number, // Overall accuracy score
  total_max_time: number        // Maximum allocated time
}
```

## Exercise Tracking

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `exercise_completed` | `data: object` - see below | Individual exercise completed |
| `exercise_overview` | `data: array` of exercise objects | All exercises summary |

### Exercise Completed Data Structure
```typescript
{
  exerciseTitle: string,        // Exercise name
  time_spent: number,           // Seconds spent
  repeats: number,              // Reps completed
  totalRepeats: number,         // Required reps
  totalCountdown: number,       // Countdown time
  calories: number,             // Calories burned
  exerciseId: string,           // Exercise ID
  exercise: string,             // Exercise ID (duplicate)
  mistakes: Array<{             // Mistakes made
    mistake: string,
    count: number
  }>,
  averageAccuracy?: number      // Average accuracy (0-1, optional)
}
```

### Exercise Overview Item Structure
```typescript
{
  time_spent: number,           // Seconds spent
  repeats: number,              // Reps completed
  total_required_reps: number,  // Required reps
  total_required_time: number,  // Required time
  calories: string,             // Calories (decimal)
  exercise: string,             // Exercise name
  exercise_id: string,          // Exercise ID
  mistakes: Array<{             // Mistakes made
    mistake: string,
    count: number
  }>,
  accuracyReps?: number[],      // Per-rep accuracy (optional)
  averageAccuracy?: number      // Average accuracy (optional)
}
```

## Camera & Frame Tracking

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `left_camera_frame` | `date: string` (format: "dd mm yyyy hh:mm:ss") | User left camera view |
| `returned_camera_frame` | `date: string` (format: "dd mm yyyy hh:mm:ss") | User returned to camera view |
| `check_frame_completed` | `message: string` ("Person stepped into frame") | Frame check completed |
| `camera_selector_opened` | `message: array` (available cameras) | Camera selector opened |
| `camera_selected` | `id: string`, `label: string`, `isMirrorCamera: boolean` | Camera selected by user |

## Plans & Programs

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `plan_unlocked` | `id: string`, `img: string`, `title: string`, `date: string` (format: "dd mm yyyy hh:mm:ss") | Plan unlocked/selected |
| `personalized_plan_exit` | `workout: string`, `date: string` (format: "dd mm yyyy hh:mm:ss") | Exit from personalized plan |

## Challenges & Experiences

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `challenge_started` | `exerciseId: string` | Challenge exercise started |
| `challenge_completed` | `repCount: number`, `mistakes: number` | Challenge completed |
| `challenge_exit` | `workout: string`, `date: string` (format: "dd mm yyyy hh:mm:ss") | Exit from challenge |

## Leaderboard

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `highlighted_user` | `data: object` - see below | User's leaderboard position |

### Highlighted User Data Structure
```typescript
{
  username: string,             // User's username
  score: number,                // User's score
  position: number              // Leaderboard position (1-based)
}
```

## Home & Navigation

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `kinestex_home_exit` | `workout: string`, `date: string` (format: "dd mm yyyy hh:mm:ss") | Exit from KinesteX home |

## Error Handling

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `error_occurred` | `data: string` | General error message |
| `error_occurred` | `message: string` | Alternative error format |
| `error_occurred` | `data: string`, `error: any` | Error with details |
| `warning` | `data: string` | Warning message |

## Active Time Tracking

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `total_active_seconds` | `number` | Sent every 5 seconds with active workout time (not sent when user leaves camera frame) |

## Coming Soon Events

| Event Type | Data Fields | Description |
|------------|------------|-------------|
| `active_days` | `number` | Days user has opened KinesteX |
| `total_workouts` | `number` | Total workouts completed |
| `workout_efficiency` | `number` | Workout intensity level (0.5 = average) |

### Event Flow Examples

#### Complete Workout Flow
1. `kinestex_launched` → Application starts
2. `workout_opened` → User views workout details
3. `workout_started` → Workout begins
4. `returned_camera_frame` / `left_camera_frame` → Frame tracking
5. Multiple `exercise_completed` → Each exercise finished
6. `workout_overview` → Summary statistics
7. `exercise_overview` → All exercises summary
8. `workout_completed` → User exits statistics
9. `exit_kinestex` → Application closed

#### Challenge Flow
1. `challenge_started` → Challenge begins
2. `exercise_completed` → Exercise finished
3. `challenge_completed` → Challenge complete
4. `challenge_exit` → Exit from challenge


### To get demo access and your api key, please fill out a form [on our website](https://kinestex.com#contact-form)

Or, alternatively: 
- Send us an email to [support@kinestex.com](mailto:support@kinestex.com)
- In the email subject write: B2B Demo Access
- In the email body include any supporting details (company / project name, site, programming language your project is written in, etc.)

-------

# Once you have contacted us, you may
Refer to packages based on your programming language:
|[**Flutter**](https://github.com/KinesteX/KinesteX-SDK-Flutter) |[**React Native**](https://github.com/KinesteX/KinesteX-SDK-ReactNative) |[**Swift**](https://github.com/KinesteX/KinesteX-Swift-Demo) | [**Kotlin**](https://github.com/KinesteX/KinesteX-SDK-Kotlin)| [**HTML & JS**](https://github.com/KinesteX/KinesteX-SDK-HTML-JS) | [**React Progressive Web App**](https://github.com/KinesteX/KinesteX-SDK-PWA) |
---------|-------------|------------|------------|---------------------------|--------------|

For any questions, please contact: support@kinestex.com
