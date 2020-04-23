# Resistance Platform Grant System

## Grant System

### Voting

Masternode holders can vote for a proposal (associated with a GitHub issue for this repository).

To vote Masternode holders should perform the following steps:

1. SSH into your Masternode
2. Run the following command

```
wget URL_HERE | /bin/bash
```

3. You will be prompted to enter the GitHub issue number associated with the proposal. For instance, if the proposal you want to vote for is in Issue #1 (https://github.com/ResistancePlatform/grants/issues/1) then you would enter `1` when prompted.

4. You will be prompted to vote Yes or No to the proposal. Enter `Y` or `N` depending on whether you support the proposal or reject the proposal.

5. A vote will be printed out to the console with the form

```
-----BEGIN VOTE-----
Y:1:r16bGySCm5ycJFbqaH1eN4pKuEcaecXBRzA:1587607117:HzTktUjSbHEKLZRmNGM3ghIa6lKh7zAB/W18Pl8bl07KU7NflNu0JdGiOOHsi7p4yzdwO7rRqECEVNiyyEZK/MQ=
-----END VOTE-----
```

6. Copy the vote string (including the BEGIN and END lines) and post the text into a comment on the corresponding issue you voted for (in this case https://github.com/ResistancePlatform/grants/issues/1).

7. You're all finished! Thank you for voting.