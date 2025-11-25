# File Upload Gateway - UI/UX Requirements Document

## Project Overview
This document outlines the UI/UX requirements for redesigning the File Upload Gateway application frontend. The application consists of two main interfaces: **Registration Page** and **Upload Gateway**. The current implementation is functional but requires a professional, standardized design following modern UI/UX principles.

---

## 1. REGISTRATION PAGE

### 1.1 Purpose
Administrative interface for registering new applications with their templates to enable file upload validation.

### 1.2 Page Structure

#### Header Section
- **Company Logo**: ICICI Bank logo (left-aligned)
- **Page Title**: "Template Registration - File Upload Gateway"
- **User Info**: Welcome message with admin avatar (right-aligned)
- **Background**: Corporate gradient (orange to dark orange)

#### Main Content Area
- **Card-based Layout**: Single centered card with rounded corners
- **Form Title**: "Register New App Template"
- **Subtitle**: "Register your application with a template to enable file upload validation."

#### Form Fields (Sequential Layout)
1. **Application Name**
   - Input Type: Text field
   - Placeholder: "Enter your application name"
   - Validation: Required field
   - Help Text: None

2. **Category**
   - Input Type: Text field
   - Placeholder: "e.g., invoice, employee, bankstatement"
   - Validation: Required field
   - Help Text: None

3. **Endpoint URL**
   - Input Type: URL field
   - Placeholder: "https://your-app.com/api/receive-data"
   - Validation: Required, valid URL format
   - Help Text: "URL where validated data will be sent"

4. **Template File**
   - Input Type: File upload
   - Accepted Formats: .csv, .xlsx, .txt
   - Validation: Required field
   - Help Text: "Upload a sample template file (CSV, Excel, or Text)"

#### Action Button
- **Primary Button**: "Register Template"
- **State Management**: 
  - Disabled/Faded when form incomplete
  - Active when all fields filled
  - Loading state during submission

#### Success State
- **Success Panel**: Expandable section showing:
  - Success message
  - Generated App Hash (copyable)
  - Integration URL (copyable)
  - Copy buttons for both values

#### Status Messages
- **Success Messages**: Green background with success icon
- **Error Messages**: Red background with error icon
- **Loading States**: Progress indicators

### 1.3 User Flow
1. Admin opens registration page
2. Fills all required form fields
3. Button becomes active when form complete
4. Submits form
5. Receives success confirmation with app hash and integration URL
6. Copies values for integration

---

## 2. UPLOAD GATEWAY

### 2.1 Purpose
End-user interface for uploading files against registered templates with validation.

### 2.2 Page Structure

#### Header Section
- **Company Logo**: ICICI Bank logo (left-aligned)
- **Page Title**: "File Upload Gateway"
- **User Info**: Welcome message with user avatar (right-aligned)
- **Background**: Corporate gradient (orange to dark orange)

#### Main Content Area
- **Card-based Layout**: Single centered card with rounded corners
- **Multi-step Process**: Three sequential sections

#### Step 1: Template Selection
- **Section Title**: "Select Template"
- **Category Dropdown**: 
  - Dynamic loading from backend
  - Placeholder: "Select Category"
  - Error handling for no available templates

#### Step 2: Template Preview (Conditional Display)
- **Section Title**: "Template Preview"
- **Template Information**:
  - Template name with file type
  - Data preview table (first 5 rows)
  - "...and X more rows" indicator
- **Download Button**: 
  - Positioned top-right of preview area
  - Downloads template file
  - Loading states during download

#### Step 3: File Upload
- **Section Title**: "Upload File"
- **File Selection**:
  - File input field
  - Accepted formats: .csv, .xlsx, .txt
- **Upload Button**:
  - Disabled/Faded until file selected
  - Active when file selected
  - Loading state during upload

#### Status Messages
- **Success Messages**: Green background with success icon
- **Error Messages**: Red background with error icon
- **Loading States**: Progress indicators

### 2.3 User Flow
1. User accesses gateway via integration URL with app parameter
2. System loads available categories for the app
3. User selects category from dropdown
4. Template preview displays automatically
5. User downloads template (optional)
6. User selects file to upload
7. Upload button becomes active
8. User uploads file
9. System validates and processes file
10. Success/error feedback displayed

---

## 3. DESIGN SPECIFICATIONS

### 3.1 Color Palette
- **Primary Orange**: #F47920 (buttons, accents, headers)
- **Dark Orange**: #E65100 (hover states)
- **Gradient**: Linear gradient from #f36f21 to #b03912 (header)
- **Success Green**: #d4edda (background), #155724 (text)
- **Error Red**: #f8d7da (background), #721c24 (text)
- **Background**: #f5f5f5 (page background)
- **Card Background**: #ffffff
- **Text Primary**: #333333
- **Text Secondary**: #555555
- **Text Muted**: #666666
- **Border**: #e1e5e9

### 3.2 Typography
- **Font Family**: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif
- **Headings**: 
  - H2: 1.3rem, font-weight: 500, color: #F47920
  - H3: 1.1rem, font-weight: 600, color: #333
- **Body Text**: 1rem, line-height: 1.6
- **Labels**: font-weight: 500, color: #555
- **Help Text**: 0.85rem, color: #666

### 3.3 Spacing & Layout
- **Container**: Max-width 800px, centered
- **Card Padding**: 2rem
- **Field Spacing**: 1.5rem between form groups
- **Border Radius**: 
  - Cards: 12px
  - Buttons: 8px
  - Inputs: 8px
- **Shadows**: 
  - Cards: 0 4px 20px rgba(0,0,0,0.1)
  - Header: 0 2px 6px rgba(0,0,0,0.18)

### 3.4 Interactive Elements

#### Buttons
- **Primary Button**: 
  - Background: #F47920
  - Padding: 0.75rem 1.5rem
  - Border-radius: 8px
  - Hover: #E65100 with slight lift effect
- **Disabled State**: 30% opacity, no pointer events
- **Loading State**: Spinner with "Loading..." text

#### Form Inputs
- **Text Inputs**: 
  - Padding: 0.75rem
  - Border: 2px solid #e1e5e9
  - Focus: Border color #F47920
- **File Inputs**: Same styling as text inputs
- **Dropdowns**: Same styling as text inputs

#### Status Messages
- **Success**: Green background, dark green text, rounded corners
- **Error**: Red background, dark red text, rounded corners
- **Padding**: 0.75rem
- **Border-radius**: 6px

### 3.5 Responsive Design
- **Mobile Breakpoint**: 768px
- **Mobile Adjustments**:
  - Reduced padding (1.5rem instead of 2rem)
  - Stack elements vertically
  - Full-width buttons
  - Adjusted font sizes

---

## 4. COMPONENT SPECIFICATIONS

### 4.1 Header Component
- **Height**: Auto (based on content + padding)
- **Padding**: 10px 32px
- **Logo Height**: 44px
- **User Avatar**: 32px circle with initials
- **Responsive**: Logo and user info stack on mobile

### 4.2 Card Component
- **Background**: White
- **Border-radius**: 12px
- **Shadow**: 0 4px 20px rgba(0,0,0,0.1)
- **Sections**: Separated by 1px border (#eee)

### 4.3 Form Components
- **Field Group**: Label + Input + Help text
- **Label**: Above input, font-weight 500
- **Input Focus**: Orange border, no outline
- **Validation**: Real-time for required fields

### 4.4 Table Component (Template Preview)
- **Header**: Orange background (#F47920), white text
- **Rows**: Alternating background (#FFF8F0)
- **Hover**: Light orange background (#FFE0B2)
- **Border**: 1px solid #ddd

### 4.5 Status Components
- **Success Panel**: Light orange background (#fff3e0)
- **Copy Buttons**: Small orange buttons with hover effects
- **Hash Display**: Monospace font, read-only inputs

---

## 5. INTERACTION PATTERNS

### 5.1 Progressive Disclosure
- Template preview only shows after category selection
- Success information only shows after successful registration
- Upload button only active when file selected

### 5.2 Loading States
- Button text changes during loading
- Disabled state during processing
- Spinner or progress indicators where appropriate

### 5.3 Feedback Mechanisms
- Immediate validation feedback
- Clear success/error messages
- Copy confirmation for hash/URL values
- File selection confirmation

### 5.4 Error Handling
- Graceful degradation for network issues
- Clear error messages for user actions
- Retry mechanisms where appropriate

---

## 6. ACCESSIBILITY REQUIREMENTS

### 6.1 WCAG Compliance
- **Level AA compliance** minimum
- **Color contrast ratios** meet WCAG standards
- **Keyboard navigation** for all interactive elements
- **Screen reader compatibility** with proper ARIA labels

### 6.2 Form Accessibility
- **Labels** properly associated with inputs
- **Required field indicators** clearly marked
- **Error messages** announced to screen readers
- **Focus management** logical tab order

### 6.3 Visual Accessibility
- **Focus indicators** visible and clear
- **Text sizing** scalable up to 200%
- **Color not sole indicator** for status/actions

---

## 7. TECHNICAL CONSIDERATIONS

### 7.1 Framework Compatibility
- Design should work with vanilla HTML/CSS/JavaScript
- No specific framework dependencies
- Progressive enhancement approach

### 7.2 Browser Support
- **Modern browsers**: Chrome, Firefox, Safari, Edge
- **Mobile browsers**: iOS Safari, Chrome Mobile
- **Graceful degradation** for older browsers

### 7.3 Performance
- **Optimized images** and assets
- **Minimal CSS/JS** footprint
- **Fast loading times** priority

---

## 8. ASSETS REQUIRED

### 8.1 Images
- ICICI Bank logo (PNG format, high resolution)
- Icons for success/error states
- Loading spinners/progress indicators

### 8.2 Fonts
- System fonts preferred for performance
- Fallback fonts specified

### 8.3 Icons
- Upload icon
- Download icon
- Copy icon
- Success/error icons
- Loading spinner

---

## 9. DELIVERABLES EXPECTED

### 9.1 Design Files
- **Figma design files** with all components
- **Component library** for reusable elements
- **Style guide** with specifications
- **Responsive layouts** for mobile/desktop

### 9.2 Assets
- **Exported images** in required formats
- **Icon set** in SVG format
- **Color palette** with hex codes
- **Typography specifications**

### 9.3 Documentation
- **Design system documentation**
- **Component usage guidelines**
- **Responsive behavior specifications**
- **Interaction state definitions**

---

## 10. CURRENT IMPLEMENTATION REFERENCE

The current implementation can be found in the `/frontend` directory with the following files:
- `register.html` - Registration page
- `index.html` - Upload gateway
- `style.css` - Current styling (reference only)
- `register.js` - Registration functionality
- `script.js` - Upload gateway functionality

**Note**: The new design should maintain all current functionality while providing a modern, professional appearance that aligns with corporate design standards.