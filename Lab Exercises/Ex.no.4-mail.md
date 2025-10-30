# Ex.No.4   MHA (Mail Header Analyzer)

## Aim
- The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.

## Procedure

### Step 1: Get the Email Header
- Copy the full, raw header from your email client.
- **Gmail:** Open the email, click the three dots (⋮), and select Show original.
- **UX Tip:** Add a smooth fade-in or fly-in animation when displaying the header pane.
- Allow users to select all text with a single button, showing an animated “Copied!” notification for feedback.

<br>
<img width="500" alt="mai1" src="https://github.com/user-attachments/assets/73149a6c-6d91-4a83-b651-4addbf4d8dff" />

<br>
orignal message:
<br>
<br>
<img width="500" alt="mail2" src="https://github.com/user-attachments/assets/0bdc44d0-209e-4db6-b2a0-255512d59af1" />

<br>
<br>

---

### Step 2: Use a Mail Header Analyzer (MHA)
- Visit an online analyzer like xheaders.com.
- **UI Animation:** Display a progress bar and animated results reveal when parsing headers.
- Paste the email header and click "Analyze."
- Many tools color-code results—green for pass, red for fail. Include micro-animations like icons popping in, checkmarks pulsing, and errors shaking.

<br>
<img width="500" alt="mail3" src="https://github.com/user-attachments/assets/74a884b4-f606-4e1d-835b-6f4e4dd7c44b" />

<br>


---

### Step 3: Analyze The Report
- Review SPF, DKIM, and DMARC results:
  - Animated icons (checkmarks, Xs) provide instant feedback.
  - Interactive tooltips pop up to explain SPF, DKIM, or DMARC fields.
- Expand delivery path, DKIM details, and errors with slide-down animations.

<br>
<img width="500" alt="mail4" src="https://github.com/user-attachments/assets/659243d4-305c-43b0-b7df-a620eaf62b49" />

<br>
<br>
<br>

##  Review the Overall Delivery Summary
- DMARC, SPF, and DKIM summaries show compliance or error with animated highlights.
- Failures shake; passes flash green briefly.

---
<br>

### Step 4: Investigate Email Path and Records
- Check why SPF passes and trace the relay path (animated email journey-style flowchart).
- Hovering on nodes pulses and shows explanatory popups.
- Confirm authorized servers and trace the route from sender to recipient.

<br>
<img width="500" alt="mail5" src="https://github.com/user-attachments/assets/10abf3ff-474f-4972-83ee-9971bc80b8ba" />

<br>
<br>
---

## Rubrics
<table style="width:50%; border-collapse:collapse;" border="1">
<tr>
<th>Criteria</th>
<th>Mark Allotted</th>
<th>Mark Awarded</th>
</tr>
<tr>
<td>1. GitHub Activity & Submission Regularity</td>
<td style="text-align:center;">3</td>
<td style="text-align:center;"></td>
</tr>
<tr>
<td>2. Application of Forensic Tools & Practical Execution</td>
<td style="text-align:center;">3</td>
<td style="text-align:center;"></td>
</tr>
<tr>
<td>3. Documentation & Reporting</td>
<td style="text-align:center;">2</td>
<td style="text-align:center;"></td>
</tr>
<tr>
<td>4. Engagement, Problem-Solving & Team Collaboration</td>
<td style="text-align:center;">2</td>
<td style="text-align:center;"></td>
</tr>
<tr>
<td><b>Total</b></td>
<td style="text-align:center;"><b>10</b></td>
<td style="text-align:center;"></td>
</tr>
</table>


## Result
- Successfully analyzed the email header using xheaders.com, verified SPF/DKIM/DMARC authenticity, traced routing from olympus.greatlearning.in via SendGrid to Google servers, and confirmed the email was genuine and not spoofed or altered.

