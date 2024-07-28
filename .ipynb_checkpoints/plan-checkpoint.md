# Video Summarizer
Video summarizer takes one or more raw input videos and creates an edited down video

## How it works
1. ~~Extract audio from the video with FFMPEG~~
2. ~~(optionally split the audio on silences and collect the timing)~~
3. ~~Pass audio clips into whisper to create a transcript~~

4. ~~Summarize the transcript with local LLM (using Llama3 instruct) (chatGPT is over-confident and will ruin the message)~~
5. ~~For each sentence in the summary find the audio clip that most closely matches~~
    - ~~embed the lines from the summary~~
    - ~~embed the lines from the transcript~~
      - add these lines to the pgvector database
6. ~~Reconstruct the summary from the clips~~, ~~just using the text for dev reasons~~
7. Ideally, we will produce a perfectly timed and produced video from these clips
~~This will probably require the accurate onset time of a these specific phrases~~

## Bonus (adjacent possible)
1. ~~Threshold by relatedness and go through in order~~
2. Eliminate flubbed takes.
   - Maybe there are umms
   - Maybe there is a misread line
   - Maybe you repeated a line until you got it
     - So in this case we would want to keep the last line that is almost the same
3. Add debug output where we see the matching lines so that we can better judge the performance of the app