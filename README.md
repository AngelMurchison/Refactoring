# Refactoring

https://github.com/AngelMurchison/Town-with-Class

public abstract class Building
    {

        public Building(string buildingType)
        {
            buildingType = this.BuildingType;
        }
        public string Name { get; set; }
        public string BuildingType { get; set; }
        public int NumberOfRooms { get; set; }
        public string ConstructionMaterial { get; set; }
        public double Height { get; set; }
        public double Width { get; set; }
        public double Length { get; set; }
        public int SquareFootage { get; set; }
        public int Floors { get; set; }
        public int BathRooms { get; set; }
        public int Volume { get; set; }
        public string Address1 { get; }
        public string Address2 { get; }
        public string city { get; }
        public string zip { get; }
        public string FullAddress
        {
            get
            {
                return $"{Address1}, {Address2}, {city}, {zip}";
            }
        }
        public int CurrentOccupants { get; set; } //incrementation, decrementation, evaluation has to be done FROM the read only property.
        public int IncreaseOccupants()
        {
            return CurrentOccupants += 1;
        }
        public int DecreaseOccupants()
        {
            return CurrentOccupants -= 1;
        }
    }
}

namespace PlayBlackjack
{
    public enum Suit
    {
        Hearts,
        Clubs,
        Diamonds,
        Spades
    } // All suits. There are 4.

    public enum Rank
    {
        Ace,
        Deuce,
        Three,
        Four,
        Five,
        Six,
        Seven,
        Eight,
        Nine,
        Ten,
        Jack,
        Queen,
        King
    } // All ranks. There are 13.

    https://github.com/AngelMurchison/PlayBlackjack

    public class Card
    {

        // allows for suit and rank to have values applied to them and be named. (inherently hardcoded int)
        public Suit suit { get; set; }
        public Rank rank { get; set; }

        // creates a variable that = each individual suit or rank
        public Card(Suit s, Rank r)
        {
            this.suit = s;
            this.rank = r;
        }

        // Creates a string value for each Card.
        public override string ToString()
        {
            return $"The {this.rank} of {this.suit}";
        }

        // Method for getting a single cards Blackjack value. Called with Card.GetCardValue
        public int GetCardValue()
        {
            var rv = 0;
            switch (this.rank)
            {
                case Rank.Ace:
                    rv = 11;
                    break;
                case Rank.Deuce:
                    rv = 2;
                    break;
                case Rank.Three:
                    rv = 3;
                    break;
                case Rank.Four:
                    rv = 4;
                    break;
                case Rank.Five:
                    rv = 5;
                    break;
                case Rank.Six:
                    rv = 6;
                    break;
                case Rank.Seven:
                    rv = 7;
                    break;
                case Rank.Eight:
                    rv = 8;
                    break;
                case Rank.Nine:
                    rv = 9;
                    break;
                case Rank.Ten:
                    rv = 10;
                    break;
                case Rank.Jack:
                    rv = 10;
                    break;
                case Rank.Queen:
                    rv = 10;
                    break;
                case Rank.King:
                    rv = 10;
                    break;
                default:
                    break;
            }
            return rv;

        }

        // Method for hitting.
        public static void Hit(List<Card> randomDeck, List<Card> Hand)
        {
            Hand.Insert(0, randomDeck[0]);
            Hand.ForEach(i => Console.Write("\n{0}\n", i));
            randomDeck.RemoveAt(0);
        }

        // Method for dealing.
        public static void Deal(List<Card> Hand, List<Card> []card1, List<Card> []card2, int total, string message)
        {
            Hand.Insert(0, card1[]);
            Hand.Insert(0, card2[]);
            int dv = Hand[0].GetCardValue() + Hand[1].GetCardValue();
            total = total + dv;
            Console.Write(message, Hand[0], Hand[0].GetCardValue());
            Console.ReadLine();
        }
    }
}
