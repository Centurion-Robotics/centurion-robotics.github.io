# Fix Slider Alignment Drift and Layout Issues in `events.html`

The goal is to fix the "progressive overlap" (alignment drift), clean up CSS syntax errors, and ensure text and images are displayed correctly without clipping.

## User Review Required

> [!IMPORTANT]
> I will be removing the "placeholder boxes" for slides without images. Instead, the slide will automatically switch to a single-column layout when no image is present, which will prevent the "missing image" confusion and give your text more room.

## Proposed Changes

### [Component] Events Page UI

#### [MODIFY] [events.html](file:///C:/Users/User/StudioProjects/centurion-robotics.github.io/events.html)

- **Fix Alignment Drift**: Add `gap: 20px` to `.slider-wrapper` to match the JS `translateX` calculation.
- **Clean Syntax**: Remove the extra `}` at line 177.
- **Improve Text Visibility**:
    - Remove `min-height: 350px` from `.slide-text-content` to prevent clipping.
    - Set `.slider-container` height to `auto` or ensure it expands to fit the tallest slide.
- **Smart Grid**:
    - Update `.slide` to use `grid-template-columns: minmax(0, 1fr) auto;`.
    - If a slide doesn't have an image, it will now occupy the full width.
- **Adjust Controls**:
    - Move `.slider-controls` to the top right of the section or increase padding to prevent overlap with the slide text.

## Verification Plan

### Manual Verification
- Verify that clicking "Next" aligns each slide perfectly with no clipping on the left or right.
- Ensure that the "Buffalo Jump" slide (no image) looks like a full-width text card.
- Ensure the "MFNERC" slide (with image) shows both the text and the photo clearly.
- Check that long text (like the SJR practice description) is fully readable.
