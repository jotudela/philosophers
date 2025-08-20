# 🚀 INTRODUCTION

The `philosophers` project at 42 school challenges students to solve the classic "Dining Philosophers" problem using thread-based solutions in the C programming language.

This project focuses on understanding multithreading, mutexes, and synchronization issues. The task involves managing concurrent threads representing philosophers who alternate between eating, thinking, and sleeping, while ensuring there are no data races or deadlocks.

![](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 🛠️ Program Specificities and Considerations

Clone my project :
```bash
git clone git@github:jotudela/philosophers.git && cd philosophers
```

> [!IMPORTANT]
> The program must handle concurrent threads efficiently, avoiding race conditions and ensuring philosophers do not starve.

> [!NOTE]
> Incorrect handling of threads or mutexes can lead to undefined behavior, such as deadlocks or starvation.

The program should :
- Simulate the dining philosophers problem with a given number of philosophers.
- Log the actions of philosophers in real-time.
- Terminate correctly when a philosopher dies or all have eaten a specified number of times.

## ⚙️ Usage

As per usual, compile like it :
```bash
make
```

to have `philo` file.

The program can be executed as follows :
```bash
./philo number_of_philosophers time_to_die time_to_eat time_to_sleep [number_of_times_each_philosopher_must_eat]
```

Little Brief of Arguments :
- `number_of_philosophers` number of philosophers and forks.
- `time_to_die` time (in milliseconds) a philosopher can live without eating.
- `time_to_eat` time (in milliseconds) a philosopher spends eating.
- `time_to_sleep` time (in milliseconds) a philosopher spends sleeping.
- `[number_of_times_each_philosopher_must_eat]` (optional) if specified, the simulation ends when each philosopher has eaten at least this many times.

Logs Format :

Each action of a philosophers is formated like this :
```bash
timestamp_in_ms X has taken a fork
timestamp_in_ms X is eating
timestamp_in_ms X is sleeping
timestamp_in_ms X is thinking
timestamp_in_ms X died
```

which `timestamp_in_ms` is the time in millisecond, and X the ID's of each philosophers.

### Core Features

The program implements the following core functionalities :
| Functionality | Brief |
|---------------|-------|
| Thread Management | - Each philosopher is represented as a thread.<br>- Forks are protected using mutexes to prevent race conditions. |
| Philosopher Behavior | - Philosophers alternate between eating, thinking, and sleeping.<br>- To eat, a philosopher must acquire the fork on their left and right.<br>- Philosophers release forks after eating and then sleep. |
| Synchronization | - Use mutexes to ensure forks are picked up and put down without conflicts.<br>- Avoid deadlocks by carefully managing the order in which forks are picked up. |
| Termination Conditions | - A philosopher dies if they fail to eat within time_to_die milliseconds.<br>- The simulation ends if all philosophers eat the specified number of times (if provided). |










