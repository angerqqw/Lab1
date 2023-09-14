using System;

class Point
{
    private double x;
    private double y;

    public Point(double x, double y)
    {
        this.x = x;
        this.y = y;
    }

    public double Dist()
    {
        return Math.Sqrt(x * x + y * y);
    }

    public string Fourth()
    {
        if (x > 0 && y > 0)
            return "Перша чверть";
        else if (x < 0 && y > 0)
            return "Друга чверть";
        else if (x < 0 && y < 0)
            return "Третя чверть";
        else if (x > 0 && y < 0)
            return "Четверта чверть";
        else if (x == 0 && y != 0)
            return "Точка на вісі Y";
        else if (x != 0 && y == 0)
            return "Точка на вісі X";
        else
            return "Початок координат";
    }

    public void Print()
    {
        Console.WriteLine($"Координати точки: x = {x}, y = {y}");
    }
}

class Program
{
    static void Main()
    {
        try
        {
            Console.Write("Введіть координату x: ");
            double x = double.Parse(Console.ReadLine());

            Console.Write("Введіть координату y: ");
            double y = double.Parse(Console.ReadLine());

            Point point = new Point(x, y);

            point.Print();

            Console.WriteLine($"Відстань від точки до початку координат: {point.Dist()}");
            Console.WriteLine($"Розташування точки: {point.Fourth()}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Помилка: {ex.Message}");
        }
    }
}
