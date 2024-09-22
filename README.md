using System;
using System.Collections.Generic;
using System.Linq;

namespace ScheduleSorting
{
    // Class to represent a schedule item
    public class ScheduleItem
    {
        public string Name { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }

        public ScheduleItem(string name, DateTime startTime, DateTime endTime)
        {
            Name = name;
            StartTime = startTime;
            EndTime = endTime;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            // Create a list of schedule items
            List<ScheduleItem> schedule = new List<ScheduleItem>()
            {
                new ScheduleItem("Meeting 1", new DateTime(2024, 3, 15, 10, 0, 0), new DateTime(2024, 3, 15, 11, 0, 0)),
                new ScheduleItem("Task A", new DateTime(2024, 3, 15, 11, 30, 0), new DateTime(2024, 3, 15, 12, 30, 0)),
                new ScheduleItem("Lunch Break", new DateTime(2024, 3, 15, 12, 30, 0), new DateTime(2024, 3, 15, 13, 30, 0)),
                new ScheduleItem("Meeting 2", new DateTime(2024, 3, 15, 14, 0, 0), new DateTime(2024, 3, 15, 15, 0, 0)),
                new ScheduleItem("Task B", new DateTime(2024, 3, 15, 15, 30, 0), new DateTime(2024, 3, 15, 16, 30, 0))
            };

            // Sort the schedule by start time
            schedule.Sort((a, b) => a.StartTime.CompareTo(b.StartTime));

            // Display the sorted schedule
            Console.WriteLine("Sorted Schedule:");
            foreach (ScheduleItem item in schedule)
            {
                Console.WriteLine($"{item.StartTime.ToShortTimeString()} - {item.EndTime.ToShortTimeString()}: {item.Name}");
            }

            Console.ReadKey();
        }
    }
}
