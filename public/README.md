# Bloop Box

Bloop Box is a collaborative project for an NFC-tag based convention game.

## History

The original idea for this game was invented by [NordicFuzzCon](https://nordicfuzzcon.org/) in 2017, known as Blip Box. Two years later, in 2019, [Furvester](https://furvester.org) implemented a very similar system which was called Boop Box. In 2020 both cons decided to join forces and create a common system, which would eventually be open-sourced and made available to any convention which might be interested in it. While the development was on-hold for two years, the entire system eventually realized close to the end of 2022. The name of this joint system is a combination of the prior independent projects.

## About the game

Enough history lessions for now, what is this game about? Well, to put it simply: Every attendee has an NFC tag assigned to them. In the case of our two conventions, the NFC tags are integrated into the convention badges, but that's is not a hard requirement.

Attendees can scan their NFC tags at the Bloop Boxes and receive achievements for different tasks. These can be for example blooping after the Guest of Honor, blooping a hundret times in ten minutes or even more obscure challenges. The limit is really only your imagination.

By collecting achievements, attendees can gather points over the course of a convention. What the convention does with that is of course completely up to them.

## Parts of the project

### Hardware

The hardware is primarily driven by a Raspberry Zero W. Several PCBs have been developed to integrate everything into a neat package. At the moment, the following repositores cover all PCBs:

- [Mainboard](https://github.com/bloop-box/bloop-box-mainboard)
  The primary interface between the Raspberry Zero W and all other components.

- [Tailboard](https://github.com/bloop-box/bloop-box-tailboard)
  Power supply and back IO.

- [LED-Board](https://github.com/bloop-box/bloop-box-led-board)
  Multi-color status indicator.

Housing of the components is at the moment up to each convention, as theming of the boxes is naturally very important to most cons.

### Software

The software side handled by a client application written in Rust. In consists of the following components:

- [Bloop Box Client](https://github.com/bloop-box/bloop-box-client)
  A small application handling all client side logic.

- [Bloop Box Data Example](https://github.com/bloop-box/bloop-box-data-example)
  An forkable example project to supply convention-specific audio files for the client.

A generic server component is not part of this project, as integration with an attendee database, achievement handling and so on are extremely unique to every convention.

The network protocol which the server has to implemente is [documented here](https://github.com/bloop-box/protocol-spec).
