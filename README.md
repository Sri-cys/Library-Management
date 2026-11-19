# PSG iTech Library - Smart Resource & Queue Management System

**Institutional Digital Library, Automated Resource Allocation & Concurrent Queue Management**  
**PSG Institute of Technology and Applied Research (PSG iTech), Neelambur, Coimbatore**

---

## Direct Portal Access & Live URLs (Apache Tomcat 9)

When Apache Tomcat 9 is running with `target/psgitech-library.war`, access the portals directly via the following explicit URLs:

* **Student & Faculty Login Page:** [http://localhost:8080/psgitech-library/login.html](http://localhost:8080/psgitech-library/login.html)
* **Librarian Portal Login Page:** [http://localhost:8080/psgitech-library/librarian-login.html](http://localhost:8080/psgitech-library/librarian-login.html)
* **Digital Library Home (Public / Post-Login):** [http://localhost:8080/psgitech-library/index.html](http://localhost:8080/psgitech-library/index.html)
* **Academic Book Catalog:** [http://localhost:8080/psgitech-library/browse.html](http://localhost:8080/psgitech-library/browse.html)
* **Librarian Smart Desk Dashboard:** [http://localhost:8080/psgitech-library/librarian-dashboard.html](http://localhost:8080/psgitech-library/librarian-dashboard.html)
* **Student My Books & Transfers:** [http://localhost:8080/psgitech-library/my-books.html](http://localhost:8080/psgitech-library/my-books.html)
* **Student Directory:** [http://localhost:8080/psgitech-library/student-directory.html](http://localhost:8080/psgitech-library/student-directory.html)
* **Student Fines & Payments:** [http://localhost:8080/psgitech-library/my-fines.html](http://localhost:8080/psgitech-library/my-fines.html)

> *Note: If Tomcat is configured to deploy as `ROOT.war` (serving directly from the port `8080` root `/`), simply omit `/psgitech-library` from the URLs above.*

---

## Quick Navigation & Portal Highlights

1. **Digital Library Home (`index.html`)**:
   - Welcome hero banner with live `Asia/Kolkata` library hours badge.
   - Quick value row linking to Catalog (`browse.html`), My Books (`my-books.html`), and Reservations (`my-reservations.html`).
   - 3 independent, scroll-snap book carousels with arrow key navigation and bounds checking:
     * *Trending Books*
     * *Recently Added*
     * *Recommended for Students*
   - Unified top navigation: `Student Directory | My Books | Browse` with `#EFECE4` active pill styling.

2. **Academic Book Catalog (`browse.html`)**:
   - Horizontal "Explore Academic Categories" card strip with instant filter toggle.
   - Two-column responsive workspace with sticky left filter card (`280px`): Category, Author, Publisher (`"e.g. Pearson"`), Department, Publication Year (`From <= To` validation with `aria-live="polite"`), and Availability.
   - Single-row toolbar with result counts, removable `#EFECE4` filter pills, sort & show size options.
   - URL query parameter state persistence (`URLSearchParams`, `pushState`, `popstate`), loading skeletons, and fixed `250px` cover framing with styled navy typographic fallback on error.

3. **Librarian Smart Desk Operations (`librarian-dashboard.html`)**:
   - Dedicated login page at `librarian-login.html` with credential verification and 2FA email OTP.
   - **Express Desk (`Alt+Shift+D`)**: Modal rapid circulation desk for high-velocity book issue and returns.
   - **Smart Operations Suite**:
     * *2D Interactive Rack Heatmap*: Live shelf utilization and circulation density maps.
     * *Predictive Collection Radar*: Syllabus surge forecasting and proactive acquisition recommendations.
     * *Trust Standing & Goodwill Extension*: Algorithmic credibility scoring ($0\text{--}100$) enabling one-click goodwill loan extensions.
     * *Exception Triage & Discrepancy Manager*: Resolves hold-shelf anomalies and unreturned items.
     * *Productivity Suite*: Acquisition request workflows, RFC 4180 bulk CSV import, and printable label sheets.
   - **11 CSV-Exportable Analytics Reports**:
     1. Circulation Velocity & Turnaround
     2. Overdue Aging Analysis
     3. Inventory Utilization & Dormant Stock
     4. Fine Realization & Waiver Audit
     5. Reservation Fulfillment Latency
     6. Departmental Resource Consumption
     7. Peak Hours Counter Traffic
     8. Lost & Damaged Attrition
     9. Student Reading Engagement Index
     10. Acquisition Pipeline ROI
     11. System Concurrency & Queue Health

---

## Default Verification Accounts

| Role | Email / Login Identifier | Password | Access Capabilities |
|---|---|---|---|
| **Admin** | `admin@psgitech.ac.in` | `AdminPassword@123` | User administration, concurrency monitor, financial overrides, full access |
| **Librarian** | `librarian@psgitech.ac.in` (`LIB101`) | `Librarian@123` | Circulation desk, Express Desk (`Alt+Shift+D`), loss assessment, replacement processing, UPI verification, fine waivers, 11 analytics reports |
| **Student** | `sivakathir.22cs@psgitech.ac.in` (`715522104045`) | `Student@123` | Digital library home, catalog, borrow history, reservation queue, peer transfer, loss reporting, replacement tracking, UPI pay |
| **Student** | `ananya.23ai@psgitech.ac.in` (`715523105012`) | `Student@123` | Digital library home, catalog, borrow history, reservation queue, peer transfer, loss reporting, replacement tracking, UPI pay |

---

## Build & Test Status

- **Technology Stack**: Core Java 17, `javax.servlet` on Apache Tomcat 9, JDBC, MySQL 8.0, HTML5/CSS3/Vanilla ES6+.
- **Automated Tests**: 382/382 passing JUnit tests (`mvn test`).
- **WAR Artifact**: `target/psgitech-library.war` generated cleanly via `mvn clean package`.
- **Project Source**: Detailed implementation documentation is available in [Library-Management/README.md](file:///Users/srisaran/Oops/Library-Management/README.md).
