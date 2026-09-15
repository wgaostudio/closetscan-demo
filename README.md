# ClosetScan demo

The published demo for [ClosetScan](https://github.com/wgaostudio/closetscan):
one phone walkthrough video beside the wardrobe catalogue generated from it.

Open `index.html` for the project overview and the interactive input/output demo.
On narrow screens the two panels stack. The garment grid and details are built
directly into the page, so no server or API key is needed. Garments and
previous/next navigation follow the order of first appearance in the video;
selecting a source timestamp seeks the video.

The catalogue has 34 garments from 68 candidate rows, with 68 generated
front/back images and attributes and narration for all 34 garments.

`phone-walkthrough.mp4` is the complete original recording transcoded to
720p H.264/AAC with recording metadata removed. Original timestamps and audio
are preserved to within container rounding. The catalogue was generated from
this compressed recording.

The saved results come from a validated DINOv2 and live paid AI run; see the
[validation summary](https://github.com/wgaostudio/closetscan/blob/main/validation/README.md)
in the main repository. `catalogue/shots` contains video frames;
`catalogue/products` contains generated images, stored as quality-95 JPEG.
Images marked as plates are generated reconstructions, not photographs; source
frames remain available for comparison. Model IDs and recorded costs in the JSON
describe that historical run, not current availability or a reproduction
guarantee. Narration includes the speaker's comments as part of this
intentionally shared example.

Keep the full catalogue directory together. The index page contains inline data
and loads its images from `catalogue/`. The MCP server in the main repository
reads the same JSON files:

```bash
python -m closetscan.mcp_server path/to/catalogue
```

Licensed MIT, as part of the main project. Visible brand marks do not imply
endorsement or grant trademark rights.
