---

title: Method and system for music program selection
abstract: In providing a music program, a personal music player displays personal activity choices. A user selects a personal activity and provides a time duration for the activity. The player sends a request to a music program server for a music program. The request includes the personal activity and the time duration. The music program server selects a music program record from a plurality of music program records that has an activity attribute which matches the personal activity and a program duration which matches or is less than the time duration. The server extracts location information for the music program from the program entry in the music program record, and sends this to the player. The player uses the location information to obtain the music program. In this manner, a music program is provided to a user based on the personal activity of the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09081375&OS=09081375&RS=09081375
owner: TP Lab, Inc.
number: 09081375
owner_city: Palo Alto
owner_country: US
publication_date: 20121113
---
This application is a continuation of co pending U.S. patent application Ser. No. 12 717 264 filed on Mar. 4 2010 which in turn is a continuation in part of U.S. patent application Ser. No. 11 714 554 filed on Mar. 5 2007 now U.S. Pat. No. 7 700 865 issued on Apr. 20 2010.

This invention relates generally to audio media particularly to method and system for selecting a music program for a personal activity.

Personal music listening experience is fundamentally enhanced with the introduction of MP3 players. The large storage capacity the ease of song downloading from a network and the sophisticated capabilities of an MP3 player provide unprecedented choices in music selection. Additionally the prolonged play time enabled by better power utilization of a MP3 player liberates a user to undertake a wide range of personal activities while listening to music from taking a walk in the neighborhood cooking a meal working out in a gym taking a 4 hour nature hike taking a bath to spending a long lazy afternoon lying on a campus lawn.

In one example Melinda goes to a gym for her 45 minute workout session in mid afternoon. She likes to listen to fast tempo and spirited music numbers that goes with her favorite high workout intensity. Using her MP3 player Melinda tries to find a XM satellite channel that provides the same. Unfortunately all she can find is a slow pace religious music program.

In another example Andy enjoys music while engaging in a variety of personal activities. In order to play the kind of music that complements the activity Andy has to spend time to put together several playlists from the vast music collection in his MP3 player. In one instant after a long and stressful day at work Andy wants to unwind in his sauna and listen to some ambient soulful music. However after shuffling through the directory of his music collection for 5 minutes Andy is able to find only half a dozen songs not quite enough to last for an hour of relaxing moment that he has in mind.

In one more example John is taking a commuter train to work in downtown New York. From his music collection in his MP3 player he plays Simon and Garfunkel s 1981 The Concert in Central Park to start his day. Unfortunately when he arrives at his office building the concert is barely half way through. John reluctantly stops the music and greets his co workers feeling unsatisfied for the rest of the morning.

The above discussion demonstrates the need for a solution to provide a music program based on the personal activity of a user.

In providing a music program a personal music player displays personal activity choices. A user selects a personal activity and provides a time duration for the activity. The player sends a request to a music program server for a music program. The request includes the personal activity and the time duration. The music program server selects a music program record from a plurality of music program records that has an activity attribute which matches the personal activity and a program duration which matches or is less than the time duration. The server extracts location information for the music program from the program entry in the music program record and sends this to the player. The player uses the location information to obtain the music program. In this manner a music program is provided to a user based on the personal activity of the user.

As will be appreciated by one skilled in the art aspects of the present invention may be embodied as a system method or computer program product. Certain aspects of the present invention may take the form of a computer program product embodied in one or more computer readable medium s having computer readable program code embodied thereon.

Any combination of one or more computer readable medium s may be utilized. The computer readable medium may be a computer readable storage medium which may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus or device or any suitable combination of the foregoing. A computer readable storage medium may be any tangible medium that can contain or store a program for use by or in connection with an instruction execution system apparatus or device.

Aspects of the present invention are described below with reference to block diagrams of methods apparatus systems and computer program products according to embodiments of the invention. It will be understood that each block of the block diagrams and combinations of blocks in the block diagrams can be implemented by computer program instructions. These computer program instructions may be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions acts specified in the block diagram block or blocks.

A user uses a personal music player to play a music program while undertaking a personal activity for time duration .

Music program is encoded in an audio digital format such as Moving Picture Experts Group 1 MPEG 1 Level 3 also known as MP3 Windows Media Audio WMA Advanced Audio Coding AAC Apple Lossless Audio Codec ALAC Pulse Code Modulation PCM or Adaptive PCM ADPCM digital format.

In one embodiment music program is a recorded music program presented by a host such as the weekly radio program MusicDeli produced by the ABC Radio National Jazztrack with Mal Stanley or Blueprint hosted by Kevin Lincoln. In one embodiment music program is a movie soundtrack such as Disney s Chicken Little Rocky Honor Picture Show produced by John Goldstone James Stewart s classic It s A Wonderful Life or Kander and Ebb s musical Chicago . In one embodiment music program is a recorded concert performance such as Simon and Garfunkel s 1981 The Concert in Central Park Elvis Presley s last live performance at Market Square Arena on Jul. 16 1977 and Peter Paul Mary 1988 reunion special A Holiday Concert produced by Public Broadcasting Service PBS .

In one embodiment music program includes a song such as John Lennon s When I m Sixty Four Jennifer Lopez s Let s Get Loud Bob Dylan s Times They Are A changing or Paul Simon and Art Garfunkel s The Boxer performed in New York City s Central Park in September 1981. In one embodiment music program includes an instrumental such as Kenny G s Forever In Love Chopin s Concerto in F Minor or Pink Floyd s Comfortably Numb performed by David Gilmour. In one embodiment music program includes comment or annotation by the host about an included song or instrumental such as the background of the composer or performer the occasion of the performance or the musical characteristics. In one embodiment the comment or annotation is before after or during an included song or instrumental.

Personal music player is a mobile audio device for personal music listening. In one embodiment user carries personal music player in a shirt pocket a purse or a backpack. In one embodiment user wears personal music player in an armband. In one embodiment user wears personal music player as part of a headset. Personal music player is capable of playing music program .

In one embodiment personal activity is taking a walk during a break. In one embodiment personal activity is cooking a dinner. In one embodiment personal activity is a work out session in a gym. In one embodiment personal activity is a meditating session after work. In one embodiment personal activity is morning commuting to work. In one embodiment personal activity is studying in a library after school. In one embodiment personal activity is reading before bedtime knitting after supper taking a shower taking a bath gardening a mile jog or doing nothing for an hour.

Music program lasts for a period of time close to time duration . In one embodiment music program lasts for 15 minutes 42 minutes 60 minutes 20 minutes or 4 minutes 32 seconds.

Personal music player includes a processor and a computer readable medium . The computer readable medium stores computer readable program code for implementing the method of the present invention.

Personal music player includes output module for playing music program . In one embodiment output module includes a wired headset. In one embodiment output module includes a wireless headset such as a Bluetooth headset. In one embodiment the wireless headset is based on other technologies such as Wi Fi Wibree ZigBee or Frequency Modulation FM technology. In one embodiment output module includes a speaker.

Personal music player includes input module for user to enter information about personal activity and time duration . In one embodiment input module includes a touch wheel a touchscreen a keypad a keyboard or a stylus. In one embodiment input module includes a microphone and speech recognition capabilities.

In one embodiment user uses input module to enter a phrase such as weight lifting workout session or reading a book . Personal music player determines personal activity based on the entered information. In one more embodiment user speaks the phrase at the microphone in input module .

In one embodiment output module includes a graphical display. Personal music player displays a plurality of personal activity choices at output module allowing user to select personal activity from the list of choices using input module . In one example as illustrated in personal music player displays personal activity choices of taking a walk preparing a meal meditating reading a book commuting and exercising . User uses input module to select one of the choices as personal activity . In one embodiment user uses the stylus in input module to select one of the choices.

In one embodiment personal music player displays a plurality of time duration choices at output module allowing user to select time duration from the list of choices. In one example personal music player displays time duration choices of 25 minutes 45 minutes 1 hour and 1 hour 20 minutes . User uses input module to select one of the choices as time duration .

In one embodiment user uses input module to enter a time such as 43 min or 1 hour 10 minutes . Personal music player determines time duration based on the entered information.

Personal music player connects to a music program server . In one embodiment personal music player connects to music program service over a data network . In one embodiment personal music player includes music program server .

The music program server includes a processor and a computer readable medium . The computer readable medium stores computer readable program code for implementing the method of the present invention.

In one embodiment data network includes the Internet. In one embodiment data network includes an Internet service provider network. In one embodiment data network includes a broadband network based on Digital Subscriber Line DSL or cable modem technology. In one embodiment data network includes a cellular based data network such as General Packet Radio Service GPRS network CDMA2000 network Wideband Code Division Multiple Access W CDMA network or third generation 3G network. In one embodiment data network includes a private network of a business entity such as a fitness center a hotel a caf or an airport. In one embodiment data network includes a home network. In one embodiment data network includes a hotspot WiFi network.

Personal music player requests music program server for a music program. Personal music player provides personal activity and time duration to music program server . In one embodiment personal music player provides personal activity and time duration using a Hypertext Transfer Protocol HTTP message. In one embodiment personal music player provides personal activity and time duration in a Remote Method Innovation RMI message. In one embodiment personal music player provides personal activity and time duration over an Application Programming Interface API .

Music program server determines music program based on personal activity and time period . Music program server sends information for music program to personal music player . In one embodiment music program server sends music program to personal music player .

Program entry includes location information for obtaining music program . In one embodiment the location information is a Web Universal Resource Identifier URI such as http www.musicprogram.com softrock musicdeli 4352.mp3. In one embodiment the location information includes an URI based on Real Time Streaming Protocol RTSP such as rtsp emusic.com 8997A9Y82.sdp. In one embodiment the location information is a file name.

Activity attribute indicates a personal activity such a taking a walk cooking commuting taking a bath or jogging .

Music program server connects to a datastore . Datastore stores a plurality of music program records that includes music program record . In one embodiment datastore includes a hard disk a flash memory. In one embodiment datastore includes a database. In one embodiment music program server includes datastore .

Music program server selects music program record wherein activity attribute matches personal activity and program duration matches time duration .

In one embodiment music program server determines that activity attribute matches personal activity if activity attribute relates to personal activity . In one example activity attribute includes cooking and personal activity is cooking a dinner . In one example activity attribute is a synonym related to personal activity . For example activity attribute is making a sandwich preparing a meal or home cooking .

In one embodiment music program server determines that program duration matches time duration if program duration is smaller than time duration . In one example program duration is 42 minutes and time duration is 50 minutes. In another embodiment music program server determines that program duration matches time duration if the difference between program duration and time duration is less than a pre determined value such as 3 minutes 5 minutes or 6 minutes. In one example program duration is 63 minutes and time duration is 60 minutes. In one embodiment music program server determines that program duration matches time duration if the difference between program duration and time duration is within 10 15 or 20 of time duration .

Music program server extracts location information for music program from program entry . Music program server sends the location information to personal music player .

In one embodiment the location information is URI . Music program server sends URI to personal music player . Personal music player uses URI to obtain music program .

In one embodiment URI is an RTSP based URI. Personal music player uses the RTSP based URI to stream music program from music program server . In one embodiment personal music player streams music program from a different server. Personal music player plays music program while streaming music program .

In one embodiment URI is an FTP based URI. Personal music player uses the FTP based URI to obtain music program in the form of an audio file such as an MP3 file a WMA file and AAC file an Audio Video Interleave AVI file or a Waveform WAV file. In one embodiment personal music player plays music program after obtaining music program in the entirety.

In one embodiment personal music player includes a storage. The storage stores music program . In one embodiment the storage is a flash drive a hard disk drive or a removable memory based on Universal Serial Bus USB or Secure Digital Card technology. In one embodiment program entry includes a title for music program . Music program server sends music program title to personal music player . Personal music player retrieves music program from the storage based on music program title.

Music program server determines music program based on personal activity and time duration . Music program includes a plurality of two or more music programs.

In one embodiment music program includes music program and music program . In one embodiment music program server connects to datastore and datastore includes music program records and . Music program record includes program entry activity attribute and program duration . Music program record includes program entry activity attribute and program duration . Program entry includes location information for music program and program entry includes location information for music program .

Music program server selects music program records and wherein both activity attributes and match personal activity and wherein the sum of program durations and match time duration . In one embodiment the sum of program durations and matches time duration if the sum is shorter than time duration . In another embodiment the sum matches time duration if the difference between the sum and time duration is less than a pre determined value or if the difference between the sum and time duration is within 10 15 or 20 of time duration .

In one embodiment music program server extracts first location information for music program from program entry and extracts second location information for music program from program entry . Music program includes the first location information and the second location information.

In one embodiment music program is a Hypertext Markup Language HTML file that includes the first location information and the second location information. Music program server generates music program and sends music program to personal music player . Personal music player uses the first location information to obtain music program and the second location information to obtain music program . In one embodiment personal music player plays music program after playing music program .

In a different embodiment music program server generates music program by combining music programs and . Music program server sends location information for music program as described in

In one embodiment music programs and are audio files in a common audio digital format such as Waveform Audio format WAV files with audio data encoded in uncompressed 16 bit mono Pulse Code Modulation PCM format at a sample rate of 44 100. As illustrated in music program includes header and data chunk . Header includes chunk size and audio data format information. Data chunk includes data chunk size and audio data . Likewise music program includes header chunk size data chunk data chunk size and audio data

Music program server combines data chunk and data chunk into data chunk of music program . Music program server stores audio data into audio data of music program and then appends audio data to audio data . Music program server computes data chunk size of music program as the sum of data chunk size and data chunk Size

Header and header are similar with a possible difference in chunk size and chunk size . Music program server copies header into header of music program and computes chunk size of music program . In one embodiment music program server computes chunk size as the file size of music program . In another embodiment Music program server computes chunk size as the file size of music program starting after the location of chunk size in the file.

In one embodiment music program server inserts a plurality of audio data before appending audio data in of music program . In one embodiment the inserted audio data represents silence for a period of time such as 3 seconds 5 seconds or 22 milli seconds. In one embodiment the inserted audio data include a music interlude. Music program server computes data chunk size and chunk size accordingly.

In one embodiment the audio digital formats of music programs and are different music program server converts music programs and to a common audio digital format before generating music program .

In one embodiment a personal activity is described using a phrase such as taking a walk . In another embodiment personal activity is described with an event name such as Rock Concert Town Hall Meeting Monday Night Football where user may attend. In one embodiment personal activity is a common activity user does normally such as going to the mall driving to work doing lunch . In one embodiment personal activity is characterized with a plurality of words describing or suggesting an activity user participates in or may participate in the future. Personal activity differs or is separate from the listening activity of the music program the usage of the media player that leads to the listening activity and or the user s interaction with the data that make up the music program s . Typically user participates in the personal activity while user enjoys listening to the music program . Further examples of personal activity include sports activities or sport events commuting activities such as driving to work taking a train commuting on a bus or commuting in a car reading activities such as reading a book reading the news reading a magazine or reading a cooking recipe shopping activities such as shopping in a mall shopping in a store or on line shopping watching activities such as watching television watching a slide show watching pictures or watching kids play in a playground dining activities such as lunch breakfast or dinner home or personal chores such as doing laundry cooking painting house cleaning or gardening leisure activities such as fishing golfing hiking sun tanning on a beach or playing a video game.

In one embodiment a reading activity includes a subject matter or a title for example the reading activity is reading the New York Times reading Harry Potter or reading a history book .

In one embodiment a sports activity or sporting event includes watching a sporting event or a type of sport such as football soccer fishing or basketball .

In one embodiment the personal music player sends a request to the music program server for a music program. The request includes a commuting activity a sports activity or a reading activity. The music program server determines music program based on the commuting activity the sports activity or the reading activity in the request as described above with reference to and . The music program server then sends the music program or the combined music program to the personal music player as described above with reference to

In one embodiment personal music player is a portable MP3 music player a mobile phone that includes a music player an electronic reading device with music playing capabilities an Internet radio an in car networked audio system and Internet audio system or a networked home entertainment system. In one embodiment personal music player is a networked computing device such as a personal computer a notebook a mini notebook or a personal digital assistant. In one embodiment the networked computing device includes a program or software that plays music program .

In one embodiment music program server is a computer server communicating with personal music player . A typical computer server includes a computing processor unit main memory storage and a network interface. In one embodiment a computer server is a computing system comprising a plurality of computer servers and a plurality of storage devices operatively coupled to each other over a network. In one embodiment a computer server is a part of the computing system. In one embodiment music program server is a computing device such as a home media center a personal computer a notebook an MP3 player or a home entertainment system.

Foregoing described embodiments of the invention are provided as illustrations and descriptions. They are not intended to limit the invention to precise form described. In particular it is contemplated that functional implementation of invention described herein may be implemented equivalently in hardware software firmware and or other available functional components or building blocks and that networks may be wired wireless or a combination of wired and wireless. Other variations and embodiments are possible in light of above teachings and it is thus intended that the scope of invention not be limited by this Detailed Description but rather by Claims following.

