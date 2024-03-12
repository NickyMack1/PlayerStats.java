# PlayerStats.java
// Abstract class for Player Statistics
abstract class PlayerStats {
    protected String playerName;
    protected int gamesPlayed;

    // Constructor
    public PlayerStats(String playerName, int gamesPlayed) {
        this.playerName = playerName;
        this.gamesPlayed = gamesPlayed;
    }

    // Getters and setters
    public String getPlayerName() {
        return playerName;
    }

    public int getGamesPlayed() {
        return gamesPlayed;
    }

}

// Subclass for Football Statistics
class FootballStats extends PlayerStats {
    private final int goalsScored;

    // Constructor
    public FootballStats(String playerName, int gamesPlayed, int goalsScored) {
        super(playerName, gamesPlayed);
        this.goalsScored = goalsScored;
    }

    // Override method to calculate average
    public double calculateAverage() {
        if (gamesPlayed == 0) {
            return 0;
        } else {
            return (double) goalsScored / gamesPlayed;
        }
    }

    // Getter and setter for goals scored
    public int getGoalsScored() {
        return goalsScored;
    }

}

// Subclass for Cricket Statistics
class CricketStats extends PlayerStats {
    private final int runsScored;

    // Constructor
    public CricketStats(String playerName, int gamesPlayed, int runsScored) {
        super(playerName, gamesPlayed);
        this.runsScored = runsScored;
    }

    // Override method to calculate average
    public double calculateAverage() {
        if (gamesPlayed == 0) {
            return 0;
        } else {
            return (double) runsScored / gamesPlayed;
        }
    }

    // Getter and setter for runs scored
    public int getRunsScored() {
        return runsScored;
    }

}

// Driver class to test the classes
public class PlayerStatsTest {
    public static void main(String[] args) {
        FootballStats footballPlayer = new FootballStats("John", 10, 7);
        CricketStats cricketPlayer = new CricketStats("Mike", 5, 150);

        // Display football player's statistics
        System.out.println("Football Player: " + footballPlayer.getPlayerName());
        System.out.println("Games Played: " + footballPlayer.getGamesPlayed());
        System.out.println("Goals Scored: " + footballPlayer.getGoalsScored());
        System.out.println("Average Goals per Game: " + footballPlayer.calculateAverage());

        System.out.println(); // Blank line

        // Display cricket player's statistics
        System.out.println("Cricket Player: " + cricketPlayer.getPlayerName());
        System.out.println("Games Played: " + cricketPlayer.getGamesPlayed());
        System.out.println("Runs Scored: " + cricketPlayer.getRunsScored());
        System.out.println("Average Runs per Game: " + cricketPlayer.calculateAverage());
    }
}

Football Player: John
Games Played: 10
Goals Scored: 7
Average Goals per Game: 0.7

Cricket Player: Mike
Games Played: 5
Runs Scored: 150
Average Runs per Game: 30.0

Process finished with exit code 0
