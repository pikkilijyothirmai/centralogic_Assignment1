using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ASSESSMENT1
{
    

class Program
        {
            static List<string> tasks = new List<string>();

            static void Main(string[] args)
            {
                bool isRunning = true;

                while (isRunning)
                {
                    Console.WriteLine("\nTask List Application");
                    Console.WriteLine("1. Create a task");
                    Console.WriteLine("2. Read tasks");
                    Console.WriteLine("3. Update a task");
                    Console.WriteLine("4. Delete a task");
                    Console.WriteLine("5. Exit");

                    Console.Write("Enter your choice: ");
                    int choice = Convert.ToInt32(Console.ReadLine());

                    switch (choice)
                    {
                        case 1:
                            CreateTask();
                            break;
                        case 2:
                            ReadTasks();
                            break;
                        case 3:
                            UpdateTask();
                            break;
                        case 4:
                            DeleteTask();
                            break;
                        case 5:
                            isRunning = false;
                            break;
                        default:
                            Console.WriteLine("Invalid choice. Please enter a number between 1 and 5.");
                            break;
                    }
                }
            }

            static void CreateTask()
            {
                Console.Write("Enter task title: ");
                string title = Console.ReadLine();
                tasks.Add(title);
                Console.WriteLine("Task created successfully!");
            }

            static void ReadTasks()
            {
                if (tasks.Count == 0)
                {
                    Console.WriteLine("No tasks available.");
                }
                else
                {
                    Console.WriteLine("Tasks:");
                    for (int i = 0; i < tasks.Count; i++)
                    {
                        Console.WriteLine($"{i + 1}. {tasks[i]}");
                    }
                }
            }

            static void UpdateTask()
            {
                ReadTasks();
                Console.Write("Enter the task number to update: ");
                int taskNumber = Convert.ToInt32(Console.ReadLine()) - 1;
                if (taskNumber >= 0 && taskNumber < tasks.Count)
                {
                    Console.Write("Enter new task title: ");
                    string newTitle = Console.ReadLine();
                    tasks[taskNumber] = newTitle;
                    Console.WriteLine("Task updated successfully!");
                }
                else
                {
                    Console.WriteLine("Invalid task number.");
                }
            }

            static void DeleteTask()
            {
                ReadTasks();
                Console.Write("Enter the task number to delete: ");
                int taskNumber = Convert.ToInt32(Console.ReadLine()) - 1;
                if (taskNumber >= 0 && taskNumber < tasks.Count)
                {
                    tasks.RemoveAt(taskNumber);
                    Console.WriteLine("Task deleted successfully!");
                }
                else
                {
                    Console.WriteLine("Invalid task number.");
                }
            }
        }








    }

