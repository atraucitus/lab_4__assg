# lab_4__assg


##hi this is a new line
class FlightTable:
    def __init__(self):
        self.matches = []
        
    def add_match(self, location, team1, team2, timing):
        self.matches.append({
            'Location': location,
            'Team 01': team1,
            'Team 02': team2,
            'Timing': timing
        })
        
    def search_by_team(self, team_name):
        team_matches = [match for match in self.matches if team_name in (match['Team 01'], match['Team 02'])]
        return team_matches
        
    def search_by_location(self, location):
        location_matches = [match for match in self.matches if match['Location'] == location]
        return location_matches
        
    def search_by_timing(self, timing):
        timing_matches = [match for match in self.matches if match['Timing'] == timing]
        return timing_matches

def main():
    table = FlightTable()
    
    table.add_match('Mumbai', 'India', 'Sri Lanka', 'DAY')
    table.add_match('Delhi', 'England', 'Australia', 'DAY-NIGHT')
    table.add_match('Chennai', 'India', 'South Africa', 'DAY')
    table.add_match('Indore', 'England', 'Sri Lanka', 'DAY-NIGHT')
    table.add_match('Mohali', 'Australia', 'South Africa', 'DAY-NIGHT')
    table.add_match('Delhi', 'India', 'Australia', 'DAY')
    
    while True:
        print("\nSearch Options:")
        print("1. List of all matches of a Team")
        print("2. List of Matches on a Location")
        print("3. List of Matches based on timing")
        print("4. Exit")
        
        choice = input("Enter your choice: ")
        
        if choice == '1':
            team_name = input("Enter the Team name: ")
            team_matches = table.search_by_team(team_name)
            print("Matches of", team_name)
            for match in team_matches:
                print(match)
                
        elif choice == '2':
            location = input("Enter the Location: ")
            location_matches = table.search_by_location(location)
            print("Matches in", location)
            for match in location_matches:
                print(match)
                
        elif choice == '3':
            timing = input("Enter the Timing: ")
            timing_matches = table.search_by_timing(timing)
            print("Matches with timing", timing)
            for match in timing_matches:
                print(match)
                
        elif choice == '4':
            print("Exiting the program.")
            break
        
        else:
            print("Invalid choice. Please select a valid option.")

if __name__ == "__main__":
    main()
