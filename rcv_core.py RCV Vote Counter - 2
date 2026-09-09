from collections import Counter

def calculate_rcv_winner(ballots):
    total_ballots = len(ballots)

    while True:
        # Step 1: First-choice vote collection
        first_choices = []
        for ballot in ballots:
            if len(ballot) > 0:
                first_choices.append(ballot[0])

        # Step 2: Count first-choice votes
        counts = Counter()
        for name in first_choices:
            counts[name] += 1

        # Step 3: Check for majority
        if len(counts) == 0:
            return None
        for candidate in counts:
            if counts[candidate] > total_ballots / 2:
                return candidate

        # Step 4: Eliminate lowest voted candidate(s)
        min_votes = min(counts.values())
        to_eliminate = []
        for candidate in counts:
            if counts[candidate] == min_votes:
                to_eliminate.append(candidate)

        # Step 5: Remove eliminated from all ballots
        for ballot in ballots:
            for elim in to_eliminate:
                while elim in ballot:
                    ballot.remove(elim)
