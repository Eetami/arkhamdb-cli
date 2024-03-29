# ArkhamDB CLI

Command-line interface for viewing decks and decklists in ArkhamDB.

By default arkhamdbcli prints cards in release order grouped by class.

## Options

* -d ARG

  Print a deck by id.

  ```sh
  arkhamdbcli -d 3645052
  ```

* -l ARG

  Print a decklist by id.

  ```sh
  arkhamdbcli -l 101
  ```

* -a

  Print class in alphabetical order.
  Combining with another -a options prints the cards in absolute alphabetical order instead.
  Can be combined with -c and -p.

* -c

  Print in cycles grouped by class.
  Can be combined with -a.

* -p

  Print in packs grouped by class.
  Can be combined with -a.

* -r

  Print cards in absolute release order.

Without -d or -l options `arkhamdbcli` will read deck as JSON from stdin.

```sh
curl -s https://arkhamdb.com/api/public/decklist/101 | arkhamdbcli
```

## ArkhamDB API

ArkhamDB CLI only supports public APIs. To print you private decks you need to fetch them
using the OAuth API yourself, and feed the JSON to `arkhamdbcli` via stdin.

## Examples

Print a popular decklist grouped by class:

```console
$ arkhamdbcli -l 47001
Kōhaku, Fifty Shades of Blurse|FHV Intro|Deck Guide (Kōhaku Narukami)
 Seeker cards
  2 × Deep Knowledge (The Innsmouth Conspiracy #23)
  2 × Fey• (A Light in the Fog #222)
  2 × Gabriel Carillo• (The Feast of Hemlock Vale Investigator Expansion #52)
  1 × Prismatic Spectacles•• (The Feast of Hemlock Vale Investigator Expansion #56)
 Rogue cards
  2 × Faustian Bargain (The Innsmouth Conspiracy #28)
 Mystic cards
  1 × Read the Signs (The Search for Kadath #117)
  1 × Spectral Razor (Dark Side of the Moon #201)
  2 × Prescient (Jacqueline Fine #19)
  2 × Promise of Power (The Innsmouth Conspiracy #32)
  2 × Armageddon (In Too Deep #117)
  1 × Read the Signs•• (The Feast of Hemlock Vale Investigator Expansion #101)
  1 × Spectral Razor•• (The Feast of Hemlock Vale Investigator Expansion #102)
  2 × The Key of Solomon•••• (The Feast of Hemlock Vale Investigator Expansion #104)
  1 × Seal of the Elders••••• (The Feast of Hemlock Vale Investigator Expansion #105)
 Survivor cards
  1 × Ancient Covenant•• (In Too Deep #122)
 Neutral cards
  2 × Guts (Core Set #89)
  2 × Perception (Core Set #90)
  2 × Backpack•• (Return to the Forgotten Age #11)
  2 × Favor of the Moon• (The Lair of Dagon #271)
  1 × In the Thick of It (Edge of the Earth Investigator Expansion #125)
  1 × Book of Living Myths (The Feast of Hemlock Vale Investigator Expansion #13)
 Weakness cards
  3 × Random Basic Weakness (Core Set #1000)
  1 × Weeping Yurei (The Feast of Hemlock Vale Investigator Expansion #14)
```

Print a popular decklist grouped by class in alphabetical order:

```console
$ arkhamdbcli -l 47001 -a
Kōhaku, Fifty Shades of Blurse|FHV Intro|Deck Guide (Kōhaku Narukami)
 Seeker cards
  2 × Deep Knowledge (The Innsmouth Conspiracy #23)
  2 × Fey• (A Light in the Fog #222)
  2 × Gabriel Carillo• (The Feast of Hemlock Vale Investigator Expansion #52)
  1 × Prismatic Spectacles•• (The Feast of Hemlock Vale Investigator Expansion #56)
 Rogue cards
  2 × Faustian Bargain (The Innsmouth Conspiracy #28)
 Mystic cards
  2 × Armageddon (In Too Deep #117)
  2 × Prescient (Jacqueline Fine #19)
  2 × Promise of Power (The Innsmouth Conspiracy #32)
  1 × Read the Signs (The Search for Kadath #117)
  1 × Read the Signs•• (The Feast of Hemlock Vale Investigator Expansion #101)
  1 × Seal of the Elders••••• (The Feast of Hemlock Vale Investigator Expansion #105)
  1 × Spectral Razor (Dark Side of the Moon #201)
  1 × Spectral Razor•• (The Feast of Hemlock Vale Investigator Expansion #102)
  2 × The Key of Solomon•••• (The Feast of Hemlock Vale Investigator Expansion #104)
 Survivor cards
  1 × Ancient Covenant•• (In Too Deep #122)
 Neutral cards
  2 × Backpack•• (Return to the Forgotten Age #11)
  1 × Book of Living Myths (The Feast of Hemlock Vale Investigator Expansion #13)
  2 × Favor of the Moon• (The Lair of Dagon #271)
  2 × Guts (Core Set #89)
  1 × In the Thick of It (Edge of the Earth Investigator Expansion #125)
  2 × Perception (Core Set #90)
 Weakness cards
  3 × Random Basic Weakness (Core Set #1000)
  1 × Weeping Yurei (The Feast of Hemlock Vale Investigator Expansion #14)
```

Print a popular decklist grouped by cycle grouped by class:

```console
$ arkhamdbcli -l 47001 -c
Kōhaku, Fifty Shades of Blurse|FHV Intro|Deck Guide (Kōhaku Narukami)
The Night of the Zealot
 Neutral cards
  2 × Guts (Core Set #89)
  2 × Perception (Core Set #90)
 Weakness cards
  3 × Random Basic Weakness (Core Set #1000)
The Dream-Eaters
 Mystic cards
  1 × Read the Signs (The Search for Kadath #117)
  1 × Spectral Razor (Dark Side of the Moon #201)
The Innsmouth Conspiracy
 Seeker cards
  2 × Deep Knowledge (The Innsmouth Conspiracy #23)
  2 × Fey• (A Light in the Fog #222)
 Rogue cards
  2 × Faustian Bargain (The Innsmouth Conspiracy #28)
 Mystic cards
  2 × Promise of Power (The Innsmouth Conspiracy #32)
  2 × Armageddon (In Too Deep #117)
 Survivor cards
  1 × Ancient Covenant•• (In Too Deep #122)
 Neutral cards
  2 × Favor of the Moon• (The Lair of Dagon #271)
Edge of the Earth
 Neutral cards
  1 × In the Thick of It (Edge of the Earth Investigator Expansion #125)
The Feast of Hemlock Vale
 Seeker cards
  2 × Gabriel Carillo• (The Feast of Hemlock Vale Investigator Expansion #52)
  1 × Prismatic Spectacles•• (The Feast of Hemlock Vale Investigator Expansion #56)
 Mystic cards
  1 × Read the Signs•• (The Feast of Hemlock Vale Investigator Expansion #101)
  1 × Spectral Razor•• (The Feast of Hemlock Vale Investigator Expansion #102)
  2 × The Key of Solomon•••• (The Feast of Hemlock Vale Investigator Expansion #104)
  1 × Seal of the Elders••••• (The Feast of Hemlock Vale Investigator Expansion #105)
 Neutral cards
  1 × Book of Living Myths (The Feast of Hemlock Vale Investigator Expansion #13)
 Weakness cards
  1 × Weeping Yurei (The Feast of Hemlock Vale Investigator Expansion #14)
Return to...
 Neutral cards
  2 × Backpack•• (Return to the Forgotten Age #11)
Investigator Starter Decks
 Mystic cards
  2 × Prescient (Jacqueline Fine #19)
```

Print a popular decklist grouped by pack grouped by class:

```console
$ arkhamdbcli -l 47001 -p
Kōhaku, Fifty Shades of Blurse|FHV Intro|Deck Guide (Kōhaku Narukami)
Core Set
 Neutral cards
  2 × Guts (Core Set #89)
  2 × Perception (Core Set #90)
 Weakness cards
  3 × Random Basic Weakness (Core Set #1000)
The Search for Kadath
 Mystic cards
  1 × Read the Signs (The Search for Kadath #117)
Dark Side of the Moon
 Mystic cards
  1 × Spectral Razor (Dark Side of the Moon #201)
Jacqueline Fine
 Mystic cards
  2 × Prescient (Jacqueline Fine #19)
The Innsmouth Conspiracy
 Seeker cards
  2 × Deep Knowledge (The Innsmouth Conspiracy #23)
 Rogue cards
  2 × Faustian Bargain (The Innsmouth Conspiracy #28)
 Mystic cards
  2 × Promise of Power (The Innsmouth Conspiracy #32)
Return to the Forgotten Age
 Neutral cards
  2 × Backpack•• (Return to the Forgotten Age #11)
In Too Deep
 Mystic cards
  2 × Armageddon (In Too Deep #117)
 Survivor cards
  1 × Ancient Covenant•• (In Too Deep #122)
A Light in the Fog
 Seeker cards
  2 × Fey• (A Light in the Fog #222)
The Lair of Dagon
 Neutral cards
  2 × Favor of the Moon• (The Lair of Dagon #271)
Edge of the Earth Investigator Expansion
 Neutral cards
  1 × In the Thick of It (Edge of the Earth Investigator Expansion #125)
The Feast of Hemlock Vale Investigator Expansion
 Seeker cards
  2 × Gabriel Carillo• (The Feast of Hemlock Vale Investigator Expansion #52)
  1 × Prismatic Spectacles•• (The Feast of Hemlock Vale Investigator Expansion #56)
 Mystic cards
  1 × Read the Signs•• (The Feast of Hemlock Vale Investigator Expansion #101)
  1 × Spectral Razor•• (The Feast of Hemlock Vale Investigator Expansion #102)
  2 × The Key of Solomon•••• (The Feast of Hemlock Vale Investigator Expansion #104)
  1 × Seal of the Elders••••• (The Feast of Hemlock Vale Investigator Expansion #105)
 Neutral cards
  1 × Book of Living Myths (The Feast of Hemlock Vale Investigator Expansion #13)
 Weakness cards
  1 × Weeping Yurei (The Feast of Hemlock Vale Investigator Expansion #14)
```

Print a popular decklist grouped by pack grouped by class in alphabetical order:

```console
$ arkhamdbcli -l 47001 -ap
Kōhaku, Fifty Shades of Blurse|FHV Intro|Deck Guide (Kōhaku Narukami)
Core Set
 Neutral cards
  2 × Guts (Core Set #89)
  2 × Perception (Core Set #90)
 Weakness cards
  3 × Random Basic Weakness (Core Set #1000)
The Search for Kadath
 Mystic cards
  1 × Read the Signs (The Search for Kadath #117)
Dark Side of the Moon
 Mystic cards
  1 × Spectral Razor (Dark Side of the Moon #201)
Jacqueline Fine
 Mystic cards
  2 × Prescient (Jacqueline Fine #19)
The Innsmouth Conspiracy
 Seeker cards
  2 × Deep Knowledge (The Innsmouth Conspiracy #23)
 Rogue cards
  2 × Faustian Bargain (The Innsmouth Conspiracy #28)
 Mystic cards
  2 × Promise of Power (The Innsmouth Conspiracy #32)
Return to the Forgotten Age
 Neutral cards
  2 × Backpack•• (Return to the Forgotten Age #11)
In Too Deep
 Mystic cards
  2 × Armageddon (In Too Deep #117)
 Survivor cards
  1 × Ancient Covenant•• (In Too Deep #122)
A Light in the Fog
 Seeker cards
  2 × Fey• (A Light in the Fog #222)
The Lair of Dagon
 Neutral cards
  2 × Favor of the Moon• (The Lair of Dagon #271)
Edge of the Earth Investigator Expansion
 Neutral cards
  1 × In the Thick of It (Edge of the Earth Investigator Expansion #125)
The Feast of Hemlock Vale Investigator Expansion
 Seeker cards
  2 × Gabriel Carillo• (The Feast of Hemlock Vale Investigator Expansion #52)
  1 × Prismatic Spectacles•• (The Feast of Hemlock Vale Investigator Expansion #56)
 Mystic cards
  1 × Read the Signs•• (The Feast of Hemlock Vale Investigator Expansion #101)
  1 × Seal of the Elders••••• (The Feast of Hemlock Vale Investigator Expansion #105)
  1 × Spectral Razor•• (The Feast of Hemlock Vale Investigator Expansion #102)
  2 × The Key of Solomon•••• (The Feast of Hemlock Vale Investigator Expansion #104)
 Neutral cards
  1 × Book of Living Myths (The Feast of Hemlock Vale Investigator Expansion #13)
 Weakness cards
  1 × Weeping Yurei (The Feast of Hemlock Vale Investigator Expansion #14)
```

Print a popular decklist in absolute release order:

```console
$ arkhamdbcli -l 47001 -r
Kōhaku, Fifty Shades of Blurse|FHV Intro|Deck Guide (Kōhaku Narukami)
  3 × Random Basic Weakness (Core Set #1000)
  2 × Guts (Core Set #89)
  2 × Perception (Core Set #90)
  1 × Read the Signs (The Search for Kadath #117)
  1 × Spectral Razor (Dark Side of the Moon #201)
  2 × Prescient (Jacqueline Fine #19)
  2 × Deep Knowledge (The Innsmouth Conspiracy #23)
  2 × Faustian Bargain (The Innsmouth Conspiracy #28)
  2 × Promise of Power (The Innsmouth Conspiracy #32)
  2 × Backpack•• (Return to the Forgotten Age #11)
  2 × Armageddon (In Too Deep #117)
  1 × Ancient Covenant•• (In Too Deep #122)
  2 × Fey• (A Light in the Fog #222)
  2 × Favor of the Moon• (The Lair of Dagon #271)
  1 × In the Thick of It (Edge of the Earth Investigator Expansion #125)
  1 × Book of Living Myths (The Feast of Hemlock Vale Investigator Expansion #13)
  1 × Weeping Yurei (The Feast of Hemlock Vale Investigator Expansion #14)
  2 × Gabriel Carillo• (The Feast of Hemlock Vale Investigator Expansion #52)
  1 × Prismatic Spectacles•• (The Feast of Hemlock Vale Investigator Expansion #56)
  1 × Read the Signs•• (The Feast of Hemlock Vale Investigator Expansion #101)
  1 × Spectral Razor•• (The Feast of Hemlock Vale Investigator Expansion #102)
  2 × The Key of Solomon•••• (The Feast of Hemlock Vale Investigator Expansion #104)
  1 × Seal of the Elders••••• (The Feast of Hemlock Vale Investigator Expansion #105)
```

Print a popular decklist in absolute alphabetical order (you madman!):

```console
$ arkhamdbcli -l 47001 -aa
Kōhaku, Fifty Shades of Blurse|FHV Intro|Deck Guide (Kōhaku Narukami)
  1 × Ancient Covenant•• (In Too Deep #122)
  2 × Armageddon (In Too Deep #117)
  2 × Backpack•• (Return to the Forgotten Age #11)
  1 × Book of Living Myths (The Feast of Hemlock Vale Investigator Expansion #13)
  2 × Deep Knowledge (The Innsmouth Conspiracy #23)
  2 × Faustian Bargain (The Innsmouth Conspiracy #28)
  2 × Favor of the Moon• (The Lair of Dagon #271)
  2 × Fey• (A Light in the Fog #222)
  2 × Gabriel Carillo• (The Feast of Hemlock Vale Investigator Expansion #52)
  2 × Guts (Core Set #89)
  1 × In the Thick of It (Edge of the Earth Investigator Expansion #125)
  2 × Perception (Core Set #90)
  2 × Prescient (Jacqueline Fine #19)
  1 × Prismatic Spectacles•• (The Feast of Hemlock Vale Investigator Expansion #56)
  2 × Promise of Power (The Innsmouth Conspiracy #32)
  3 × Random Basic Weakness (Core Set #1000)
  1 × Read the Signs (The Search for Kadath #117)
  1 × Read the Signs•• (The Feast of Hemlock Vale Investigator Expansion #101)
  1 × Seal of the Elders••••• (The Feast of Hemlock Vale Investigator Expansion #105)
  1 × Spectral Razor (Dark Side of the Moon #201)
  1 × Spectral Razor•• (The Feast of Hemlock Vale Investigator Expansion #102)
  2 × The Key of Solomon•••• (The Feast of Hemlock Vale Investigator Expansion #104)
  1 × Weeping Yurei (The Feast of Hemlock Vale Investigator Expansion #14)
```

## Caching

ArkhamDB CLI caches the loaded cards and pack list to your home directory under `~/.arkhamdb`.
To remove the cache run the following command:

```sh
rm -rf ~/.arkhamdb
```
