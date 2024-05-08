High Quality Video Encoding at Scale (https://netflixtechblog.com/high-quality-video-encoding-at-scale-d159db052746) : 
    It use an ingest API which uses several processes from initial validation to encoding in different formats. Netflix uses ec2 Amazon cloud for video processing.
    ![image](https://github.com/saikatHi6/ConceptDoc/assets/4381376/9ff8651e-421a-4f00-b937-4c4b874f752c)


1. Video Source Inspection: In this stage mainly validate video source content. If source content has any issue then immediately it throw errors and does not process.
   --The best source video available is ingested into the system. In many cases, error mitigation techniques only partially fix the problem.
    --Complex algorithms (which could have been avoided by better processes upstream) do not unnecessarily burden the Netflix ingest pipeline.
   --Source issues are detected early when a specific and actionable error can be raised.
Content partners are motivated to triage their production pipeline and address the root causes of the problems. This will lead to improved video source deliveries in the future.
![image](https://github.com/saikatHi6/ConceptDoc/assets/4381376/e08dbf94-3896-4403-9561-ec2dd7d5f124)

To guard against frame accuracy issues that may have been introduced by incorrect parallel encoding (for example, chunks assembled in the wrong order, or frames dropped or duplicated at chunk boundaries), we validate the assembled stream by comparing the spatial and temporal fingerprints of the encode with that of the source video (fingerprints of the source are generated during the inspection stage).

3. Parallel Video Encoding
   At Netflix we stream to a heterogenous set of viewing devices. This requires a number of codec profiles: VC1, H.264/AVC Baseline, H.264/AVC Main and HEVC. We also support varying bandwidth scenarios for our members, all the way from sub-0.5 Mbps cellular to 100+ Mbps high-speed Internet. To deliver the best experience, we generate multiple quality representations at different bitrates (ranging from 100 kbps to 16 Mbps) and the Netflix client adaptively selects the optimal stream given the instantaneous bandwidth.
     ![image](https://github.com/saikatHi6/ConceptDoc/assets/4381376/a9bb2cbd-2855-4757-866c-d28bc6630cb2)
