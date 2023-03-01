namespace Rock_paper_scissor
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Random random = new Random();
            int yourScore = 0;
            int enemyScore = 0;

            while (yourScore != 3 && enemyScore != 3)
            {
                Console.WriteLine(); 
                Console.WriteLine("Your score - " + yourScore + ". Computer score - " + yourScore);
                Console.WriteLine("Choose [r]ock, [p]aper,or [s]cissors");
                string yourMove = Console.ReadLine();

                int computerMove = random.Next(0, 3);

                if (computerMove == 0) 
                {
                    Console.WriteLine("The computer chose rock.");

                    switch (yourMove)
                    {
                        case "r":
                            Console.WriteLine("Draw!");
                            break;
                        case "p":
                            Console.WriteLine("You won!");
                            yourScore++;
                            break;
                        default:
                            Console.WriteLine("You lost");
                            enemyScore++;
                            break;
                    }
                }
                else if (computerMove == 1) 
                {
                    Console.WriteLine("The computery chose paper.");

                    switch (yourMove)
                    {
                        case "r":
                            Console.WriteLine("You lost");
                            enemyScore++;
                            break;
                        case "p":
                            Console.WriteLine("Draw!");
                            break;
                        default:
                            Console.WriteLine("You won");
                            yourScore++;
                            break;
                    }

                }
                else 
                {
                    Console.WriteLine("The computer chose scissors.");

                    switch (yourMove)
                    {
                        case "r":
                            Console.WriteLine("You won");
                            yourScore++;
                            break;
                        case "p":
                            Console.WriteLine("You lost");
                            enemyScore++;
                            break;
                        default:
                            Console.WriteLine("Draw!");
                            break;
                    }
                }

            }

            if (yourScore == 3)
            {
                Console.WriteLine("You win!");
            }
            else
            {
                Console.WriteLine("You lose!");
            }
        }
    }
}
