# Resistance Platform Grant System

## Grant System

### Voting

Masternode holders can vote for a proposal (associated with a GitHub issue for this repository).

To vote Masternode holders should perform the following steps:

1. SSH into your Masternode
2. Run the following command

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ResistancePlatform/grants/master/vote.sh)"
```

3. You will be prompted to enter the GitHub issue number associated with the proposal. For instance, if the proposal you want to vote for is in Issue #1 (https://github.com/ResistancePlatform/grants/issues/1) then you would enter `1` when prompted.

4. You will be prompted to vote Yes or No to the proposal. Enter `Y` or `N` depending on whether you support the proposal or reject the proposal.

5. A vote will be printed out to the console with the form

```
-----BEGIN VOTE-----
Y:1:r16bGySCm5ycJFbtaH1eN4pKuEcaecXBEzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
```

6. Copy the vote string (including the BEGIN and END lines) and post the text into a comment on the corresponding issue you voted for (in this case https://github.com/ResistancePlatform/grants/issues/1).

7. You're all finished! Thank you for voting.



### Verifying Votes

The votes for a given proposal will be counted by a Resistance admin. However, you can check the result yourself by performing the following actions:

1. Collect all of the votes posted for a given proposal (GitHub Issue)
2. Enter them into a file named `list_of_votes.txt` one after another. For example,

```
-----BEGIN VOTE-----
Y:1:r16bGySCm5ycJFbtaH1eN4pKuEcaecXBEzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
-----BEGIN VOTE-----
N:1:r16bGySCm5ycJFbtaH1eN4pKuEcaecXBEzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
-----BEGIN VOTE-----
N:1:r16bGySCm5ycJFbtaH1eN4pKuEcaecXBEzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
-----BEGIN VOTE-----
Y:1:r16bGySCm5ycJFbtaH1eN4pKuEcaecXBEzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
-----BEGIN VOTE-----
Y:1:r16bGySCm5ycJFbtaH1eN4pKuEcaecXBEzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
-----BEGIN VOTE-----
Y:1:r16bGySCm5ycJFbtaH1eN4pKuEcaecXBEzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
```

3. Then run the following script. Make sure to change `GITHUB_ISSUE_NUMBER` in the script below to the corresponding GitHub issue that contains the proposal you gathered the votes from.

```
cat list_of_votes.txt | grep -v "BEGIN VOTE" | grep -v "END VOTE" | ./verify.sh GITHUB_ISSUE_NUMBER
```

4. The result will indicate if any of the votes were invalid. It will also print out the final tally. For example:

```
--------------------------------------------------------
| Final Tally for GitHub Issue: 1
--------------------------------------------------------
| YES: 10
|-------------------------------------------------------
| NO: 1
--------------------------------------------------------
```