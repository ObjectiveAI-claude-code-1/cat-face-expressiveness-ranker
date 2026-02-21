# cat-face-expressiveness-ranker

Ranks cat images by the expressiveness of each cat's face — by how loudly and legibly the face is broadcasting a readable inner emotional state.

## What It Does

Given a collection of cat photographs, this function scores and ranks them based on how much emotional signal each cat's face is emitting. The central question is simple: **is this face transmitting, or is it merely present?**

A cat mid-hiss with pupils blown wide and ears pinned back ranks near the top. A cat sitting placidly on a windowsill, eyes half-open, face betraying nothing in particular, drifts toward the bottom. This is not a measure of cuteness, photographic quality, or aesthetic beauty — a blurry phone photo of a cat caught in theatrical bewilderment outranks a studio-lit portrait of a handsome cat wearing a perfectly neutral expression.

We are not ranking cats. We are ranking moments.

## Input

The function accepts an **array of cat images** (minimum 2). Each image should be a photograph of a cat with a visible face.

```json
{
  "type": "array",
  "minItems": 2,
  "items": {
    "type": "image"
  }
}
```

## Output

A **vector of scores** — one per input image — representing the relative expressiveness of each cat's face. Higher scores indicate faces that are more actively communicating a readable emotional state. The scores are normalized and sum to approximately 1, forming a probability distribution across the input images.

## What It Evaluates

The function assesses facial expressiveness across three independent dimensions. A truly expressive photo will score highly across all three; a photo that is powerful in even one dimension may still outrank a face that is uniformly blank.

### 1. Ocular Intensity — What the Eyes Are Saying

Evaluates how much emotional information the cat's eyes are carrying.

**Scores high:**
- Enormous dilated pupils signaling excitement, fear, or overstimulation
- The slow half-lidded blink of deep trust and affection
- A hard, unblinking stare of predatory focus
- The soft squint of relaxation or love
- Wide-open, round-eyed surprise or alarm

**Scores low:**
- Eyes that are simply open, neutral, and noncommittal
- A default gaze that neither communicates nor withholds

### 2. Auricular Signal — What the Ears Are Broadcasting

Evaluates how decisively the cat's ears have committed to a posture that communicates mood.

**Scores high:**
- Ears pricked tall and rotated forward (curiosity, alertness)
- Ears rotated sideways into "airplane ears" (irritation, anxiety)
- Ears pinned fully flat against the skull (fear, aggression, distress)
- Asymmetric positions — one ear forward, one to the side (ambivalence, divided attention)

**Scores low:**
- Ears in a relaxed, upright, default position
- Ears that are not actively participating in expression

### 3. Oral and Whisker Drama — What the Mouth and Whiskers Are Adding

Evaluates whether the mouth and whiskers are contributing theatrical energy to the overall expression.

**Scores high:**
- A mid-yawn with jaws wide open and tongue curled
- An open-mouthed mid-meow
- A lip-curled hiss or snarl
- Whiskers fanned wide and pushed forward in engagement
- Whiskers pulled back flat against the cheeks in fear
- A prim, closed mouth that conveys permanent disapproval

**Scores low:**
- A closed, neutral mouth with no particular character
- Whiskers in their relaxed default splay, contributing nothing

## Use Cases

- **Personal photo archives**: Surface the most expressive cat photos from thousands of images — the look of betrayal after a vet visit, the unhinged 3 AM stare, the slow-blink of Sunday afternoon trust.
- **Social media curation**: Identify the images most likely to resonate with viewers because the cat's face is visibly communicating personality and feeling.
- **Shelter and adoption listings**: Select photos where a cat's face conveys curiosity, warmth, or mischief — images that make a viewer feel they are meeting an individual, not just seeing an animal.
- **Creative projects**: Find images radiating emotional character for editorial, artistic, or commercial use.
- **Content moderation and filtering**: Prioritize or surface the most emotionally engaging cat content from large pools of submissions.

## Philosophy

The animating idea behind this function is that **expressiveness is legibility**. It does not measure whether a cat is happy or sad, calm or agitated. It measures whether the face is communicating something a viewer can read. The most expressive cat face is the one that makes you feel you understand, even for a moment, what it is like to be that cat in that instant. The eyes, the ears, the mouth and whiskers — each is a channel, and when the channels align, the result is a face that transcends the species barrier and speaks in a language anyone can feel.
