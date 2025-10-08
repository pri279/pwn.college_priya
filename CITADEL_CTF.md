# Zahard's Welcome

## Challenge Description

The base of Citadel rises before you, its great doors sealed with fractured steel and dead circuitry. Faded corporate protocols still hum in the lock, relics of the world that fell.

Those who came before tried to climb but all failed. Their echoes linger as fragments of voices, reminders of broken attempts to free humanity. Now you have chosen to take their place. You will be the one to scale the Citadel and finish what they could not.

The voices of the fallen whisper through the static: "The path begins in the gathering place. There, candidates are chosen". Here is your invitation.

Step into the gathering place where all climbers are briefed before the ascent.

## Solve

**Flag:** `citadel{7h3_c174d3l_b3ck0n5}`

The flag was visible in the rules channel of the discord server link provided. 


# The Social Network

## Challenge Description
🗼OSINT pt1: The ascent begins. The first floor is not metal or binaries but of memory. Among the echoes, one voice lingers, of an early climber. He was among the earliest to challenge the Citadel, and though he failed, his traces remain scattered across the ruins of the old world.

It is said that the key to the next floor can be found by tracing the socials of this legendary climber.

Start by checking out citadweller on Instagram.

## Solve
**Flag:** `citadel{17_1s_jus7_7h3_b3g1nn1ng}`

The description gave the first instruction which was to find the citadweller account on instagram. On finding the account, the story highlight on the page had the first part of the flag and citadweller's X account which gave me the second part of the flag.


# track 8

## Challenge Description
Bypassing the second chamber leads to an empty floor except for a single artifact in the center: an old MP3 player, scratched and worn. On its surface, a cipher is etched, a message left behind for anyone who can decode it

`twj eys zpr ukm 'viamnwqw' bx lzgo: esmqqui{yyr_oshwwcm_bwupa}`

When you power it on, the sound fills the chamber. The tracks play like whispers from a lost world, and you recognize it as a song from Panchiko’s latest studio album, particularly track no. 8. Its title feels familiar, hinting at a famous cipher. Decrypt it by using the album name as your key and continue your ascent.

## Solve
**Flag:** `citadel{add_vinegar_twice}`

The description gave me the clue to find Panchiko's latest album: Ginkgo having track no 8 'Vinegar' which hinted that it could be vigenere cipher. I used an online vigenere decoder with 'Ginkgo' as the key, the decoded text was "now use the key 'panchiko' on flag: rigckmv{osd_ikumqog_tjkjm}". Using this clue and decoding once again, I was able to obtain the flag.

## New Learnings
I learned what vingere cipher was.


# Omniscient Flag's Metadata

## Challenge Description
As you step into the second chamber, a figure manifests. Before you stands a forgotten deity, a dead god spoken of only in whispers. Known by countless names: “Apostle of Epilogue and Eternity”, “Lone Messiah” and many more lost to time.

They leave nothing but a single image, a relic carrying his final secret. Hidden within its layers lies the key to ascend to the next chamber.

## Solve
**Flag:** `citadel{th1s_ch4ll3ng3_1s_f0r_th4t_0n3_ex1ft00l_4nd_b1nw4lk_enthus14st}`

The challenge gave us an image challenge.jpg and description mentioned metadata, I figured the flag might be hidden in the image properties. So on running exiftool command, the author tag that said  “kdj had a habit of hiding images within images” which implied steganography was the way forward.

## New Learnings
I learnt how to use exiftool command to view metadata and a few methods of steganography.


# Test of Sweetness

## Challenge Description
This floor feels like a digital world. The space is an illusion, all pink and sweet, stretching around you in impossible patterns. Here, you are no longer a climber but just another user.

Ahead, a door glows faintly. It is the only path forward and requires a level of authority you do not yet have. Fragments of session memory flicker, hinting at what it might take to gain higher access.

Challenge: https://testofsweetness.citadel.cryptonitemit.in/

## Solve
**Flag:** `citadel{fru1tc4k3_4nd_c00k13s}`

On visiting the site, I was given a clue saying, "How does a website remember you?" The answer was using cookies. On changing the value of the user cookie to "admin", I was able to obtain the flag.


# Rotten Apple

## Challenge Description
Among the debris of this floor, you find a relic of sound: An album which turns out to be D>E>A>T>H>M>E>T>A>L by Panchiko, a long lost album. But the music is warped, as though it has undergone disc rot.

The path forward is hidden in the distortion. Similar to how the album was warped, the password to the next floor has been warped first by a factor of 47, then by a factor of 13. Untangle these changes to reveal the code and continue your ascent.

`4:R256=Y3oRRoP0#~%Ro?A`

## Solve
**Flag:** `citadel{b3tt3r_ROTt3n}`

The challenge description hinted at rot and two numbers, 47 and 13. This implied I should use ROT13 and ROT47 to obtain the flag. Using CyberChef to decode, I obtained the following values:

On applying ROT13: `4:E256=L3bEEbC0#~%Eb?N`
On applying ROT47: `citadel{b3tt3r_ROTt3n}` 

## New Learnings
I got to learn about decoding ROT47 and ROT13.


# Randomly Accessed Memories

## Challenge Description
On your ascent to this floor, you hear these fragments being played back
```
clone it, pull it, reset it, stage it,
commit, push it, fork, rebase it,
merge it, branch it, tag it, log it,
add it, stash it, diff, untrack it.
```
You look around and discover a chamber containing a vast archive of Daft Punk’s music, intertwined with cryptic commits left behind by other musicians. They seem ordinary at first glance, but not everything in the history is what it seems.

## Solve
**Flag:** `citadel{w3_4r3_up_4ll_n1t3_t0_g1t_lucky}`


# Selected Ambient Work

## Challenge Description
The symphonic adventure does not end here. On the next floor, a single song keeps echoing through the floor, repeating in a haunting loop. Amid the sound, you find a note left by a past candidate. It hints that the song holds a secret message, hidden in plain sight, much like how Aphex Twin concealed his face within his music with the help of spectrograms.

To move forward, you must find the message hidden in this sound.

Note: Separate the words in the flag with _ and make it UPPERCASE. Example: citadel{S3L3CT3D_AMB13NT_W0RK}

## Solve
**Flag:** `citadel{1_LOV3_1DM}`

Using Audacity, spectogram view, we found out which frequencies the morse code tones were producing. This part was kind of cool because I could see the morse patterns in the audio waves. So we filtered the audio using an equilizer and ran it through a translator. It turns out the message was a bunch of information about Richard David James but there was one part of the message that didn't look like it belonged: "1 LOV3 1DM". That looked suspicious so I tried that out as the flag, and it worked.


# The Robot's Trail

## Challenge Description
You enter a virtual maze, a labyrinth of shifting corridors and endless paths. A guardian robot patrols the floor, leaving a trail behind as it moves. Follow the path it carves, trace its movements carefully, and uncover the key it leads you to. Only by following the robot’s trail can you reach the door to the next floor.

Challenge: https://therobotstrail.citadel.cryptonitemit.in

## Solve
**Flag:** `citadel{p4th_tr4v3rs4l_m4st3ry_4ch13v3d}`

In the website, there were a bunch of decoy buttons but there was a hint to change display from none, so I switched that option to all. On doing so, a new option came up, leading me to the file robots.txt. 
On appending the file locations to the website URL a few times, I finally got to the flag.txt which gave me the flag.


# Rotting in the Deep

## Challenge Description
The floor is quiet, almost unnervingly so – like the Citadel has paused to take your measure. A soft ring of presence settles around the chamber, the kind that marks a true landing: from here, it will ask for more and, in return, grant more. Etched into its surface is a sequence of numbers, worn and faint, as if time itself is eating them away. A whisper from the echoes guides you:

The message lies beneath the surface. Push it three steps forward in the cycle of life, and only then will the words emerge from the void.

## Solve
**Flag:** `citadel{br0_r34lly_unr0tt3d_m3_b4ck_t0_l1f3}`


# Coco Conjecture

## Challenge Description
The door to the next floor is guarded by a figure who calls herself "The Dragon CEO". She does not speak of mercy or choice, only of order and efficiency.

To enter the next chamber, you must complete the task presented by her. Complete it exactly as instructed, achieving operational efficiency by her standards, and the path forward will open.

Connection: nc chall_citadel.cryptonitemit.in 61234

## Solve
**Flag:** `citadel{k1ryu_c0c0_h4s_4_g0_4t_4n_uns0lv3d_m4th3m4t1cs_pr0bl3m}`


# schlagenheim

## Challenge Description
Your quest continues, but you feel something odd about this room. The only artifact on this floor is a corrupted file held in the hands of a jet-black statue, frozen in the pose of a band mid-performance. The passcode to the next floor is hidden within this piece of music, but it can’t be played, as if the wrong extension has scrambled it.

You must take the corrupted file and repair it to reveal the true code that will unlock the door forward.

## Solve
**Flag:** `citadel{8lackM1D1wa5c00l}`

This challenge came with a mysong.wav file which I opened using Audacity and tried to check if the spectogram gave any clues. So, using `hexdump -C mysong.wav` we saw the magic bytes. The hex code was `4d 31 44 31` which doesn't match any file type but we noticed that it read M1D1 in ASCII. This implies that the file was supposed to be a midi file and thus I tried to edit the file signature by using `hexedit mysong.wav` in order to change the magic bytes to the regular midi file signature `4d 54 68 64`. After this I redefined the file type using `mv mysong.wav mysong.mid`. Then we checked the patterns that the MIDI sequences have and the pattern displayed was the flag.

## New Learnings
I learned that file signatures were defined using magic bytes.


# XOR Slide

## Challenge Description
You realise that a previous climber has set up a puzzle in what was otherwise an empty room, blocking the entrance to the next floor on the ceiling. You must slide the blocks forming the pyramid to create a path above.

## Solve
**Flag:** `citadel{pyr4m1d+x0r}`


# The Sound of Music

## Challenge Description
🗼OSINT pt2: citadweller had a newfound interest in tracking the music they last listened to and posting ratings of new albums on various online platforms.

The flag is hidden in these digital footprints across music platforms and split into three segments. You will need to find all three to uncover the complete code and move on to the next floor.

## Solve
**Flag:** `citadel{c0mputers_st0pped_exchang1ng_1nf0rmat10n_n_started_shar1ng_st0r1es_n_then_they_were_n0where_t0_be_f0und}`

This challenge was easy because we'd already found the last two parts while stalking the citadweller in OSINT pt1. We first found part 2 on rateyourmusic and found part 3 on spotify. Part 3 took us a bit but we finally found it on lastfm and combined all 3 parts to get the complete flag.


# Echoes and Pings

## Challenge Description
You come across the remnants of a fallen corporation and the final network communication ever sent by them.

Allegedly, the message contained an image that predicted the rise of the Citadel. Your task is to uncover what was sent and decode the communication to extract the passcode that will unlock the next floor.

## Solve
**Flag:** `Citadel{l_r34lly_w4nt_t0_st4y_4t_y0ur_h0us3}`


# The Ripper

## Challenge Description
The guardian of this floor steps from the shadows. Known only as Jack the Ripper, he watches you carefully. He proclaims himself merciful and hands you a word list to help. He asks you to find the passcode hidden in the file. The word list is your only aid. Only by combining the two correctly, can you uncover the key and move on to the next floor.

Flag format: citadel{password}

## Solve
**Flag:** `citadel{fake_flag_4_fake_pl4y3rs}`

First, we identified what type of hash we were dealing with. The hash began with `$2a$04$` which meant this was a bcrypt hash. The `$2a$` indicates the bcrypt algorithm and `04` represents the cost factor. Since Jack the Ripper provided a wordlist, this had to be a password cracking and had to find which word from the list when hashed with bcrypt, would produce the given hash. So, we used hashcat with mode 3200 (bcrypt) to systematically test each word in the list against the target hash:

```
echo '$2a$04$RNoyoWAcW0StwSri4YN1Eeb2j1gBNKutDOMxsLzfyfSvB/ghMHToa' > hash.txt
hashcat -m 3200 -a 0 hash.txt wordlist.txt
```
The tool quickly found the matching password, revealing the flag.


# AetherCorp NetprobeX

## Challenge Description
You step into a simulation of the past, entering the ruins of AetherCorp, the most ambitious corporation in history, and their creation, NetProbeX, once the most advanced networking tool the world had ever seen. The floor reconstructs the events that led to humanity’s downfall.

Your task is to find the hidden backdoor in NetProbeX, the flaw that triggered the collapse. By uncovering it, you can reverse the damage and retrieve the passcode to advance to the next floor.

Engineers left faint traces in the logs — small, odd markers where separators once sat. Read these traces as if they divide commands.

Challenge: http://chall_citadel.cryptonitemit.in:32772/

## Solve
**Flag:** `citadel{bl4ck51t3_4cc3ss_gr4nt3d}`


# Feels Like We Only Go Backwards

## Challenge Description
After finding the backdoor and making your way to the next floor, you step into a chamber awash with shifting colors and swirling echoes, a concert frozen in time. Kevin Parker stands at the center, his riffs bending reality around him. To ascend, you’ll need to join the session on his terms: push your voice further than comfort, align yourself with the number he hides in the haze, and piece together the melody concealed within layers of reverb. Only then will the music open the way upward.

## Solve
**Flag:** `citadel{f0r_0n3_m0r3_h0ur_1_c4n_r4g3}`

The first level `kevin wants you to sing your heart out, it could be some music to walk home by:` , type in `music to walk home by` to go to the next level.
For the second level, enter 8168008137 to go to the next level. 
For the third level, execute the following python program:

```sh
encoded_data = [
    0x00c9, 0x00de, 0x00fd, 0x00e0, 0x00e7, 0x00ea, 0x00f9, 0x0120,
    0x00ff, 0x009c, 0x0121, 0x00fc, 0x009f, 0x0124, 0x00b7, 0x0118,
    0x0135, 0x00bc, 0x0141, 0x00cc, 0x012d, 0x0148, 0x00d9, 0x0164,
    0x015f, 0x0142, 0x00ef, 0x0154, 0x015d, 0x0100, 0x0175, 0x0160,
    0x0103, 0x0107, 0x010b, 0x010f, 0x010b
]

memory_bytes = [
    # 0x2370: 03 07 0B 0F 0B 07 03 07 0B 0F 0B 07 03 07 0B 0F
    0x03, 0x07, 0x0B, 0x0F, 0x0B, 0x07, 0x03, 0x07,
    0x0B, 0x0F, 0x0B, 0x07, 0x03, 0x07, 0x0B, 0x0F,
    # 0x2380: 0B 07 03 07 0B 0F 0B 07 03 07 0B 0F 0B 07 03 07
    0x0B, 0x07, 0x03, 0x07, 0x0B, 0x0F, 0x0B, 0x07,
    0x03, 0x07, 0x0B, 0x0F, 0x0B, 0x07, 0x03, 0x07,
    # 0x2390: 8F 01 1C 01 83 01 1C 01 (but we only need 5 more bytes)
    0x8F, 0x01, 0x1C, 0x01, 0x83
]

def decode_flag():
    flag = ""
    for i in range(37):
        # input_char[i] = (encoded_data[i] - 5 * i - memory_bytes[i]) / 2
        input_char = (encoded_data[i] - (5 * i) - memory_bytes[i]) // 2
      
        if 32 <= input_char <= 126:
            flag += chr(input_char)
        else:
            flag += f"[{input_char:02x}]"
  
    return flag

result = decode_flag()
print(f"Decoded flag: {result}")
print(f"Length: {len(result)}")

# The flag seems to be related to Tame Impala lyrics
# "for one more hour I can..." appears to be part of it
# Let me check what the complete flag should be
```

# Database Incursion

## Challenge Description
After your legendary battle with the artist, the virtual world has returned, stretching around you in endless grids and flickering data, you find a rogue data terminal and on careful inspection, you find you’re able to inject rogue structured queries. Using this critical vulnerability, find a way to extract the hidden passcode.

Challenge: https://databaseincursion.citadel.cryptonitemit.in

## Solve
**Flag:** `citadel{wh3n_w1ll_y0u_f1nd_0u7_1f_175_5ql_0r_53qu3l?}`


# BRATCHA
A clear chime rolls through the chamber and a new crest ignites on your badge – a quiet promotion. The outer ring is behind you. From here, the Citadel opens its inner systems, and the locks grow heavier because the keys are worth more. Your answers now carry more weight – and earn more in return. The citadel welcomes you to the inner climb.

Near the gate to the next floor you come across a CAPTCHA verification test, but it has been covered by scratches on the decaying wall and misleading letters stopping you from finding the correct key, all to prove you’re human.

## Solve
**Flag:** `citadel{1m_3v3rywh3r3_1m_s0_jul1a}`


# A Memory's a Heavy Burden

## Challenge description
You now find yourself in the place where many climbers have been laid to rest. A cold wind moves through the temple grounds, carrying whispers of the departed. Stone lanterns and marble graves reflect Buddhist traditions, their shadows stretching across the frost-covered earth.

The temple rests in the shadow of a very iconic mountain, quiet and imposing. Every detail in the image, the arrangement of the graves, the lanterns, and the lingering scent of incense, holds clues to its true location. You need to uncover the exact coordinates of where you are to move on from here.

Note: round off coordinates to 3 decimal places.

Flag format: citadel{XX.XXX_XXX.XXX}

## Solve
**Flag:** `citadel{35.486_136.699}`


# Case Sensitivity

## Challenge Description
You step into a constricted floor where every movement and operation is limited. Commands are few, space is tight, and options are restricted.

A guardian looms over the floor, its body shifting like liquid metal, enforcing these constraints. It watches your every move, daring you to make do with what you have and uncover the passcode to the next floor despite the restrictions.

Connection: nc chall_citadel.cryptonitemit.in 32770

## Solve
**Flag:** `citadel{d34th_d035_n07_fr33_y0u_fr0m_7h3_gu17ar15t}`


# Viral Bionic Anomaly

## Challenge Description
This floor is haunted by a phantom of the past. You encounter a presentation created by the last employee of a forgotten corporation, made just minutes before the Citadel awoke.

Rumor has it that the corporation predicted the rise of the Citadel. Within the slides, a "starter pack" holds the clues you need. Use it to confront the "final boss", a threat trapped inside a macro hidden deep within the presentation, and claim the key to the next floor.

## Solve
**Flag:** `citadel{gr4b_y0ur_l4bubus_m4tch4s_4nd_dub41_ch0c0l4t3s_y0u_4r3_1n_f0r_4_r1d3}`

The challenge came with a file: challenge.pptm. The ppt told us we had to look into the macros to figure out how to beat the performative male final boss so we looked into the macro view of the file and saw the code used to encode the flag. We saw that the message was split across multiple variables (a1-a21, b1-b26, C1-c18) and had undergone 3 different encoding schemes to encrypt the flag. 
The three functions were `ZqL9D8()`, `JvQ1g()`, and `Yu89()` and on searching those up, we figured out they were Base32, Base58, and Base64 decoders respectively. 
In the end, the macro combined all three functions in order to get the flag. But since we couldn't run the code, we concatenated each section separately.

First, we combined all the strings a1 to a21 and decoded them from base32 (in cyberchef) into hex code. 
Then we tried converting the combined hex from the 'a' and 'b' variables but that resulted in an error. Finally, we decoded them from hex using cyberchef and got the proper hex code to use. On testing the concatenated variables, we got half the image, which gave me the flag.


