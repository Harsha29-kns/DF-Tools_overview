# Ex.No.4   MHA (Mail Header Analyzer)
# 🌐 Website Used: [xheaders.com](https://xheaders.com/)
## Aim
- The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.

## Procedure

### Step 1: Get the Email Header
- Copy the full, raw header from your email client.
- **Gmail:** Open the email, click the three dots (⋮), and select Show original.
- **UX Tip:** Add a smooth fade-in or fly-in animation when displaying the header pane.
- Allow users to select all text with a single button, showing an animated “Copied!” notification for feedback.

<br>
<img width="1909" height="884" alt="mai1" src="https://github.com/user-attachments/assets/73149a6c-6d91-4a83-b651-4addbf4d8dff" />

<br>
orignal message:
<br>
<br>
<img width="1919" height="875" alt="mail2" src="https://github.com/user-attachments/assets/0bdc44d0-209e-4db6-b2a0-255512d59af1" />

<br>
<br>

---

### Step 2: Use a Mail Header Analyzer (MHA)
- Visit an online analyzer like xheaders.com.
- **UI Animation:** Display a progress bar and animated results reveal when parsing headers.
- Paste the email header and click "Analyze."
- Many tools color-code results—green for pass, red for fail. Include micro-animations like icons popping in, checkmarks pulsing, and errors shaking.

<br>
<img width="1686" height="841" alt="mail3" src="https://github.com/user-attachments/assets/74a884b4-f606-4e1d-835b-6f4e4dd7c44b" />

<br>


---

### Step 3: Analyze The Report
- Review SPF, DKIM, and DMARC results:
  - Animated icons (checkmarks, Xs) provide instant feedback.
  - Interactive tooltips pop up to explain SPF, DKIM, or DMARC fields.
- Expand delivery path, DKIM details, and errors with slide-down animations.

<br>
<img width="1894" height="883" alt="mail4" src="https://github.com/user-attachments/assets/659243d4-305c-43b0-b7df-a620eaf62b49" />

<br>
<br>

#### Review the Overall Delivery Summary
- DMARC, SPF, and DKIM summaries show compliance or error with animated highlights.
- Failures shake; passes flash green briefly.

---

### Step 4: Investigate Email Path and Records
- Check why SPF passes and trace the relay path (animated email journey-style flowchart).
- Hovering on nodes pulses and shows explanatory popups.
- Confirm authorized servers and trace the route from sender to recipient.

<br>
<img width="1857" height="397" alt="mail5" src="https://github.com/user-attachments/assets/10abf3ff-474f-4972-83ee-9971bc80b8ba" />

<br>
<br>

---

## Technical Info for Deeper Analysis

- **From/To/Subject/Date:** Basic sender/receiver and timestamp info.
- **Received:** Tracks journey across mail servers—helps trace spoofing or relay problems.
- **Return-Path/Reply-To:** Shows bounce or reply addresses; used for authenticity checks.
- **SPF, DKIM, DMARC:** Authentication mechanisms—crucial for anti-spoofing and trust.
- **MIME-Version and Content-Type:** Indicates email format and content support.
- **Message-ID:** Unique identifier for each mail—useful for tracking and diagnostics.
- **X-Spam-Score, X-Mailer:** Shows spam risk and mail client information for further review.

---

## Result
# Email Header Analysis Result

## Email Subject
**Reset your Olympus password**

---

## Authentication Status

| Method     | Result      | Details                                                                 |
|------------|-------------|-------------------------------------------------------------------------|
| SPF        | Pass        | The sending server (149.72.189.153) is authorized for the domain.       |
| DKIM       | Pass        | DKIM signature verified; email unchanged and signed with sender's key.  |
| DMARC      | Pass        | DMARC policy enforced and authentication checks aligned.                |

- **DKIM Authentication:** PASS  
  - The email content has not been tampered with since signing.
  - Domain: `greatlearning.in`
  - Selector: `s1`
  - Algorithm: `rsa-sha256`
  - Signed Header Fields: date, from, subject, mime-version, content-type, to, etc.

---

## Delivery & Relay Information

- **No originating IP address found in header** (possible privacy feature).
- **Received delay:** 1 second.
- **Email Path:**
  - Sent from: `olympus.greatlearning.in` (149.72.189.153)
  - Routed via: `wrqvbdww.outbound-mail.sendgrid.net`
  - Received by: Google's servers (`mx.google.com`), then relayed to the recipient.

| Hop | Delay      | From                                   | Server/Info                          |
|-----|------------|----------------------------------------|--------------------------------------|
| 1   | 0 seconds  | olympus.greatlearning.in               | geopod-ismtpd-18 (ESMTP)             |
| 2   | 0 seconds  | recvd-5fb5cd787f-5wk2n                 | SMTP relay                           |
| 3   | 0 seconds  | wrqvbdww.outbound-mail.sendgrid.net    | mx.google.com (TLS encrypted)        |
| 4   | 0 seconds  | 2002:ac8:5fc4:0:b0:4ae:f855:77b0       | SMTP relay                           |
| 5   | *          | 2002:a05:7010:7acd:b0:485:30c4:c8bc    | SMTP                                 |

---

## Additional Header Insights

- **SPF Not Aligned:** The SPF record did not fully match the visible From domain, but DKIM alignment compensates.
- **Mismatched Sender Information:** The From address doesn't match Return-Path, a potential sign of spoofing or forwarding.
- **X-Mailer / User-Agent:** Not present.
- **Spam Score:** Not available.

---

## Technical Summary

- **SPF (Sender Policy Framework):** Verifies sending server authorized to send for domain[web:32][web:31].
- **DKIM (DomainKeys Identified Mail):** Ensures content is unchanged and signed by a valid sender key[web:32][web:31].
- **DMARC (Domain-based Message Authentication, Reporting & Conformance):** Ensures that at least SPF or DKIM are aligned with the visible domain and enforces policies for failed authentication[web:32][web:31][web:33].

  > All three authentication methods report **PASS**: this message is verified as authentic and safe, although a minor address mismatch exists.

---

## Security Notes

- No blacklists detected for the sender IP.
- SPF/DKIM/DMARC passed: High confidence in sender legitimacy.
- Mismatched addresses can sometimes occur with legitimate email relays or forwarding.

---

**Conclusion:**  
The email is authenticated and DMARC compliant, with both SPF and DKIM passing validation. Minor sender mismatches are likely not a threat due to successful cryptographic checks and recognized relay. No signs of spoofing, blacklisting, or tampering detected[web:32][web:31][web:33].
