from fpdf import PDF

class PDF(FPDF):
    def header(self):
        self.set_font("Arial", "B", 14)
        self.cell(0, 10, "UPSC CSE 2-Year Detailed Timetable for Night-Shift Working Aspirants", ln=True, align="C")
        self.ln(5)

    def chapter_title(self, title):
        self.set_font("Arial", "B", 12)
        self.set_text_color(0)
        self.cell(0, 10, title, ln=True, align="L")
        self.ln(2)

    def chapter_body(self, body):
        self.set_font("Arial", "", 10)
        self.multi_cell(0, 10, body)
        self.ln()

pdf = PDF()
pdf.add_page()

# Add content
pdf.chapter_title("👤 Candidate Profile")
pdf.chapter_body("""
- Working Hours: 9:00 PM – 8:00 AM (Night Shift)
- Free Time: 8:00 AM – 9:00 PM (Except Sleep & Personal Time)
- Target: UPSC CSE (Prelims + Mains + Interview)
- Timeline: 24 Months (Balanced and Realistic)
- Coaching: Self-preparation
""")

pdf.chapter_title("⏰ Daily Routine (Weekday)")
pdf.chapter_body("""
8:00 AM – 8:30 AM: Light breakfast, relax after shift
8:30 AM – 3:30 PM: Sleep
3:30 PM – 4:00 PM: Freshen up, tea/snack
4:00 PM – 6:00 PM: Session 1 – GS Subject (Core Study)
6:00 PM – 7:00 PM: Break/Dinner
7:00 PM – 8:30 PM: Session 2 – Optional / CSAT / Answer Writing
8:30 PM – 9:00 PM: Get ready for office
9:00 PM – 8:00 AM: Work Hours
During work breaks: Newspaper, podcasts, revise current affairs
""")

pdf.chapter_title("📚 Booklist for UPSC CSE – Self Preparation")
pdf.chapter_body("""
General Studies Paper I:
- Polity: Indian Polity – M. Laxmikanth
- Modern History: Spectrum – Rajiv Ahir
- Ancient & Medieval History: Old NCERTs – R.S. Sharma, Satish Chandra
- Geography: NCERTs + Goh Cheng Leong
- Economy: Ramesh Singh + Budget + Economic Survey
- Environment: Shankar IAS Book
- Art & Culture: Nitin Singhania
- Science & Tech: NCERTs 6–10 + Current Affairs
- Current Affairs: The Hindu/Indian Express, Vision/Insights PDFs

CSAT:
- RS Aggarwal + Previous Year Papers

Essay & Ethics:
- Lexicon for Ethics
- Essay Compilations by Vision/ForumIAS
""")

pdf.chapter_title("🎯 Year-Wise Plan")
pdf.chapter_body("""
Year 1 (Month 1–12): Build Foundation
- Months 1–4: NCERTs, Newspaper Reading, Start Optional
- Months 5–8: Standard GS Books, Continue Optional, Begin CSAT
- Months 9–12: Revise basics, Start Prelims MCQs & Answer Writing

Year 2 (Month 13–24): Practice & Revision
- Months 13–16: Mains Topics, Daily Answer Writing
- Months 17–20: Prelims Focus, MCQ Practice, Weekly Mocks
- Months 21–24: Mains Focus, Optional, Essay, Ethics, Mock Interviews
""")

pdf.chapter_title("📅 Weekly Subject Plan")
pdf.chapter_body("""
Monday: GS - Polity | Optional Subject
Tuesday: GS - Modern History | Optional + Notes
Wednesday: GS - Geography | CSAT Practice
Thursday: GS - Economy | Optional / Case Studies
Friday: GS - Environment | CSAT / Revision
Saturday: GS - Sci & Tech / Art & Culture | Weekly Current Affairs Recap
Sunday: Full-Length Mock | Essay / Answer Writing
""")

pdf.chapter_title("✅ Tips to Succeed While Working")
pdf.chapter_body("""
- Use work breaks for light reading or current affairs
- Keep one day/week light to avoid burnout
- Monthly self-assessments are key
- Practice mock tests regularly
- Prioritize consistent revision for retention
""")

pdf.output("UPSC_CSE_2_Year_Timetable_Working_Professional.pdf")
