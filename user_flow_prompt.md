# Flowchart Prompt for Meta Business Settings User Flow with Authenticator App

## Prompt for Flowchart Creation Tool:

Create a detailed flowchart for the Meta Business Settings user flow from login to launching an Advantage+ Shopping Campaign with Shopify integration. Include the improved two-factor authentication flow with authenticator app recommendations.

## Flow Structure:

### 1. Login & Two-Factor Authentication Flow

**Start:** User accesses Meta Business Settings
- Input: Email and Password
- Decision: 2FA Method Selected?
  - Option A: SMS (Default)
    - Send SMS code to registered phone number
    - Display: Phone number +81 90-****-5678
    - Timer: Start 30-second countdown
    - Decision: Code received within 30 seconds?
      - Yes: Input 6-digit code → Validate → Success: Proceed to Business Selection
      - No: Display troubleshooting options
        - **RECOMMENDED: Download Authenticator App** (Highlighted path)
          - Substep 1: Choose app (Google Authenticator/Microsoft Authenticator/Authy)
          - Substep 2: Scan QR code or enter manual code
          - Substep 3: Enter 6-digit code from app
          - Substep 4: Setup complete → Proceed to Business Selection
        - Alternative 1: Receive code via Email
          - Send email code → Input code → Validate → Proceed to Business Selection
        - Alternative 2: SMS Troubleshooting checklist
          - Check phone number correctness
          - Wait 1-2 minutes
          - Check spam/blocked messages
          - Check carrier settings (docomo/au/SoftBank specific)
          - Resend SMS (max 2 times)
          - If still failing → Contact Support
        - Alternative 3: Contact Support (Chat/Phone)
  
  - Option B: Authenticator App (If previously set up)
    - Open authenticator app
    - Display: Enter 6-digit code
    - Timer: Show 30-second refresh timer
    - Input code → Validate → Success: Proceed to Business Selection

### 2. Business Portfolio Selection Flow

**Step:** Select Business Portfolio
- Display: List of available businesses with details:
  - Business Name
  - Business ID
  - Creation Date
  - Last Updated
  - **Connected Ad Accounts** (Count + Details)
    - For each ad account show:
      - Ad Account Name
      - Ad Account ID (act_XXXXXXXXXX)
      - Status (Active/Paused/Disabled)
      - Monthly Budget
      - Last Used Date
  - Connected Assets Summary:
    - Facebook Pages (count)
    - Instagram Accounts (count)
    - Pixels (count)
    - Catalogs (count)

- Decision: Business has Ad Account?
  - **Yes**: Display business with "RECOMMENDED" badge → User selects → Proceed to Asset Verification
  - **No**: Display warning "⚠️ No ad account connected"
    - Show info modal: "Why do I need a Business Portfolio?"
      - Explain: Business vs Personal account differences
      - Show: Your situation selector
        - "I have a business account" → Select business
        - "I use a personal account" → Show migration guide
        - "I don't know" → Start guided setup
    - Options:
      - Add existing ad account to business
      - Create new ad account
      - Contact Support

- Special Case: Personal Ad Account Detected
  - Display notification: "⚠️ Personal ad account found (act_XXXXXXXXXX)"
  - Show: "Not connected to any business"
  - Explain: "Advantage+ campaigns require business portfolio"
  - Required action:
    - Step 1: Create business portfolio (2 min)
    - Step 2: Migrate ad account (1 min)
    - Step 3: Add required assets (3 min)
  - Buttons:
    - "Start guided setup" (Recommended)
    - "Watch video tutorial (3 min)"
    - "Manual setup"
    - "Contact support"

- Filter Options Available:
  - Show only businesses with ad accounts
  - Show only recently used
  - Show only with Shopify integration
  - Sort by: Last updated / Creation date / Name

### 3. Asset Verification & Configuration Flow

**Step:** Verify Required Assets
- Show checklist with current status:
  - ✅ Facebook Page: [Name] or ❌ Not connected
  - ✅ Instagram Account: [@handle] or ❌ Not connected
  - ✅ Pixel: [ID - Active/Inactive] or ❌ Not created
  - ⚠️ Catalog: Multiple detected or ❌ Not created
  - ✅ Email: [email@domain.com] or ❌ Not verified
  - ❌ Commerce Manager: Not configured (if e-commerce)
  - ⚠️ Team Members: Review permissions

**Pixel Selection Subprocess:**
- Decision: Pixel exists?
  - Yes: Display list of pixels with:
    - Pixel ID
    - Connected domain
    - Status (Active/Inactive with colored indicator)
    - Last data received timestamp
    - "RECOMMENDED" badge on most recently active
    - Options: [Use this] [Delete]
  - No: Create new pixel flow

**Instagram Connection Subprocess:**
- Decision: Instagram connected?
  - Yes: Show @handle and connection status
  - No: 
    - Button: "Login with Instagram"
    - Info message: "Business account required"
    - Link: "How to convert to business account"

**Catalog Management Subprocess:**
- Decision: Catalog exists?
  - Yes: Display catalog list with:
    - Catalog name
    - Business association
    - Product count
    - Last updated timestamp
    - Data source (Shopify/CSV/Manual)
    - Active campaigns using this catalog
    - Status indicator
    - **Duplicate detection**: "⚠️ Same products in multiple catalogs"
      - Option to merge/consolidate
      - Select master catalog
  - No: Create new catalog flow

- Special: Multiple Catalogs Detected
  - Show comparison table
  - Highlight recommended catalog
  - Options:
    - Use existing catalog
    - Create new catalog
    - Merge catalogs
    - Delete unused catalogs

### 4. Shopify Integration Flow

**Step:** Connect Shopify Store
- Prerequisite check:
  - Business selected? → Yes/No
  - Ad account connected? → Yes/No
  - Required assets ready? → Yes/No
  
- If prerequisites incomplete:
  - Show warning with missing items
  - Options:
    - Complete setup now (guided)
    - Complete setup later
    - Contact support

- Integration Process:
  - Substep 1: "Install Meta App" on Shopify
  - Substep 2: Redirect to Meta → Login confirmation
  - Substep 3: **Select Business Portfolio** (with ad account details shown)
  - Substep 4: **Select/Confirm Assets**:
    - Pixel selection (auto-detect if available)
    - Catalog selection/creation
      - Option: "Sync products from Shopify automatically"
      - Show preview of products to be synced
    - Facebook Page confirmation
    - Instagram Account confirmation
  - Substep 5: Permission grants:
    - Allow Meta to access Shopify product data
    - Allow automatic product sync
    - Set sync frequency
  - Substep 6: Final confirmation screen:
    - Business: [Name]
    - Ad Account: [ID and Name]
    - Pixel: [ID]
    - Catalog: [Name - X products]
    - FB Page: [Name]
    - IG Account: [@handle]
    - Review all settings
    - Button: "Connect and Continue"

### 5. Advantage+ Shopping Campaign Creation Flow

**Step:** Create Campaign
- Pre-flight check display:
  - ✅ Business configured
  - ✅ Ad account active
  - ✅ Pixel installed and receiving data
  - ✅ Catalog synced (X products)
  - ✅ Shopify connected
  - ✅ Payment method verified

- Campaign Setup:
  - Enter campaign name
  - Select campaign objective (Sales - Auto-selected)
  - Set budget and schedule
  - Select catalog for product promotion
  - Set target audience (or use Advantage+ auto-targeting)
  - Review and launch

**End:** Campaign Successfully Created
- Show success message
- Display campaign dashboard
- Show next steps and optimization tips

### 6. Error Handling & Support Points

Throughout the flow, always show:
- Contextual help (?) icons
- "Contact Support" button (Chat/Phone)
- "Watch Tutorial" video links
- "FAQ" links
- Progress indicator showing current step
- "Save Draft" option for long processes
- "Back" button to return to previous step

### Decision Point Format:
- Use diamond shapes for decisions
- Use rectangles for processes
- Use parallelograms for input/output
- Use rounded rectangles for start/end
- Use different colors for:
  - Recommended paths (Green)
  - Warning/Issues (Yellow/Orange)
  - Errors/Blocks (Red)
  - Alternative paths (Blue)
  - Support/Help (Purple)

### Special Annotations:
- Mark "RECOMMENDED" paths with ⭐ or highlighted border
- Mark "WARNING" states with ⚠️
- Mark "ERROR" states with ❌
- Mark "SUCCESS" states with ✅
- Mark "OPTIONAL" steps with (Optional) label
- Show estimated time for each major step
- Show help/info available at each step

## Additional Notes:
- Emphasize the authenticator app path as the recommended solution
- Show all alternative paths clearly
- Indicate which steps can be skipped vs. required
- Show where users commonly get stuck
- Include timeout/session management notes
- Include data validation points
