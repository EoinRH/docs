A cosine similarity matrix is built from all our email segments which gives a similarity score for any 2 segments marked 'relevant' in our data.

Methodology devised from data exploration and score comparisons:
### Segments have similarity score of 1.0: 
- **Intuition**: This is the same exact piece of information with no changes.
- **Action**: Keep only the first received
### Segments have similarity score of 0.98:
- **Intuition**: Almost identical, likely formatting difference. Very low chance of significant difference.
- **Considerations**: 
	- Likelihood of significant difference increases the further apart they are received. 
	- Subject is poor indicator of duplication
- **Action**: 
	- Segments received within the same week?
		- Keep first received
	- Otherwise keep both.
#### **Examples** 
1. Similarity: 0.98 | **Different subject** | Received 1 week apart | Action: Keep Both
	- 2024-11-28: 136297.
		- Summary: According to Infolink’s latest price release, the N-type wafer price stayed flat at CNY1.03/slice. The N-type module price stayed flat at CNY0.71/slice and the N-type cell price increased 3.7% to CNY0.28/slice. The 182mm cell and 210mm cell prices stayed flat ==**WoW**== at CNY0.275/W and CNY0.28/W, respectively. The polysilicon ASP dropped 1.3% WoW to ==**CNY39.5/kg**==. The 182mm wafer price stayed flat at CNY1.15/slice, and 210mm wafer price stayed flat WoW at CNY1.70/slice. The 182mm and 210mm mono module prices stayed flat WoW at CNY0.68/W and CNY0.69/W respectively. We maintain our Neutral view on the solar sector, which we downgraded in December 2022, likely the first broker to have a non-positive sector rating for the sector.
	- 2024-12-05: 153777
		- Summary: According to Infolink’s latest price release, the N-type wafer price stayed flat at CNY1.03/slice. The N-type module price stayed flat at CNY0.71/slice and the N-type cell price stayed flat at CNY0.28/slice. The 182mm cell and 210mm cell prices stayed flat at CNY0.275/W and CNY0.28/W, respectively. The polysilicon ASP dropped 1.3% WoW to ==**CNY39.0/kg**==. The 182mm wafer price stayed flat at CNY1.15/slice, and 210mm wafer price stayed flat at CNY1.70/slice. The 182mm and 210mm mono module prices stayed flat at CNY0.68/W and CNY0.69/W respectively.
2.  Similarity: 0.99 | **Different Subject** | Received 2 days apart | Action: Keep first only
	- 2025-01-18: 238922
		- Corn Oil, domestic Used Cooking Oil and Tallow get low emission scores. It's our preliminary understanding that Distillers Corn oil will get an emission score of 13. This translates into total PTC of $0.74/gal. Under 45Z, Corn oil will be getting nearly 50c/gal more than soybean oil. We estimate RD made from domestic Used Cooking oil as well as Tallow will have **==an==** emission intensity of 18-19. This translates into total PTC of $0.62 - $0.64/gal. Under 45Z, domestic UCO / tallow will be getting nearly ~40c/gal more than soybean oil.
	- 2025-01-16: 231987
		- Corn Oil, Domestic Used Cooking Oil and Tallow get low emission scores. It's our preliminary understanding that distillers **==of==** Corn oil will get an emission score of 13. This translates into total PTC of $0.74/gal. Under 45Z, Corn oil will be getting nearly 50c/gal more than soybean oil. We estimate RD made from domestic Used Cooking oil as well as Tallow will have emission intensity of 18-19. This translates into total PTC of $0.62 -$0.64/gal. Under 45Z, domestic UCO / tallow will be getting nearly ~40c/gal more than soybean oil.

### Segments have a similarity score of <0.98
- **Intuition**: Matches in this bracket largely fall into templated emails which appear frequently. Increasingly difficult to design programmatic filters.
- **Action**: Keep both matches
##### **Example:** Many minor number changes:
- Similarity: 0.97 | **Same subject** | Received more than 1 week apart | Action: Keep Both
	- 2024-10-05: 15817
		- Cancelled sailings came down to ==**12.8**==% (vs. **==14.4==**% last week), above previous year level of ==**10.1**==%. Total number of scheduled sailings increased c.+2% YoY, however, Asia-West Coast scheduled sailings are c.23% higher than last year. Idling rate remains at ==**3.8**==% by TEU (vs. 3.8% last week) this week, below ten-year average at 4.5% by TEU. Schedule reliability slightly improved in August to 52.8% (vs 52.1% in July), and average delay days of late vessels increased to 5.28 days (vs 5.24 days in July).
	- 2024-10-17: 32447
		- Cancelled sailings came down to ==**9.8**==% (vs. ==**12.8**==% last week), above previous year level of ==**6.7**==%. Total number of scheduled sailings increased c.+2% YoY; however, Asia-West Coast scheduled sailings are c.23% higher than last year. Idling rate increased to ==**3.9**==% by TEU (vs. 3.8% last week) this week, below ten-year average at 4.5% by TEU. Schedule reliability slightly improved in August to 52.8% (vs 52.1% in July), and average delay days of late vessels increased to 5.28 days (vs 5.24 days in July).