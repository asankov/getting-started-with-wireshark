# 03. Configuring the Wireshark Interface

## Wireshark Profiles

Profiles are different configuration of the Wireshark interface.

For example, different colours for the packets, different columns, etc.

### Columns

We can add new columns to our view via `Wireshark` -> `Preferences` -> `Appearance` -> `Columns`.

Data can be extracted from a packet to a column via `Apply as Column` option from the data view.

### Colouring

We can color different packets in different ways.

To apply a color to a package, we need a display filter.
For example, `tcp.flags.syn==1` that finds all TCP SYN packets.

We can then set the colors via `View` -> `Colouring rules...`.

### Screen Layout

We can adjust the Screen Layout via `Wireshark` -> `Preferences` -> `Appearance` -> `Layout`.

## Questions

1. Add a coloring rule that will make your tcp FIN packets blue. What filter will you use to do that?

   ```text
   tcp.flags.fin==1
   ```

2. Select packet number 1. Can you find the TCP segment length? Add this value as a column.

   ```text
   0
   ```

3. It would be nice to have a button that quickly filters for all TCP Errors. See if you can find the TCP Retransmission we were looking at earlier. How can you filter for all TCP errors in the trace file? What is this filter?

   In the bottom of the packet info we have a `[SEQ/ACK analysis]` section.
   This information is not part of the packet, but is derived by Wireshark to help us.

   All information that is in brackets - `[]` is not part of the packet, but is derived by Wireshark.

4. Add the TCP Errors filter as a button in this profile.

5. It can be a little overkill to see timestamps all the way to the nanosecond. Using the View | Time Display Format menu option, can you see how to configure Wireshark to only display to the microsecond?

   `View` -> `Time Display Format` -> `Hundredths of a second`
