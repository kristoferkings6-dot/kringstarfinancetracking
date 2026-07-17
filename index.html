import React, { useState, useMemo } from "react";
import {
  AreaChart, Area, BarChart, Bar, LineChart, Line, PieChart, Pie, Cell,
  XAxis, YAxis, Tooltip, ResponsiveContainer, CartesianGrid,
} from "recharts";
import {
  TrendingUp, TrendingDown, DollarSign, Wallet, PiggyBank, Users,
  FileText, Target, Activity, Bell, Search, ChevronDown, ChevronLeft,
  ChevronRight, Download, ArrowUpRight, ArrowDownRight, Compass,
  LayoutGrid, PieChart as PieIcon, CreditCard, TrendingUp as Growth,
  AlertTriangle, CheckCircle2, Clock, Filter, Percent, Building2,
} from "lucide-react";

/* ---------------------------------------------------------
   TOKENS
   bg-base #0B0F17 · surface #131826 · surface-2 #1A2033
   gold #E3B341 (positive/wealth) · rose #E5484D (negative/risk)
   teal #2DD4BF (secondary/growth) · text #F3F5F9 · muted #8A93A6
   Display: Space Grotesk · Body: Inter · Data: JetBrains Mono
--------------------------------------------------------- */

const fonts = `
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap');
`;

const COLORS = {
  base: "#0B0F17",
  surface: "#131826",
  surface2: "#1A2033",
  border: "rgba(255,255,255,0.08)",
  gold: "#E3B341",
  rose: "#E5484D",
  teal: "#2DD4BF",
  text: "#F3F5F9",
  muted: "#8A93A6",
};

const PIE_COLORS = ["#E3B341", "#2DD4BF", "#8B7FE8", "#E5484D", "#5B9BD5", "#6B7280"];

function naira(n, compact = false) {
  if (compact) {
    if (Math.abs(n) >= 1_000_000) return `₦${(n / 1_000_000).toFixed(1)}M`;
    if (Math.abs(n) >= 1_000) return `₦${(n / 1_000).toFixed(0)}K`;
  }
  return `₦${n.toLocaleString("en-NG", { maximumFractionDigits: 0 })}`;
}

/* ---------------------------------------------------------
   DEMO DATA
--------------------------------------------------------- */

const months = ["Feb", "Mar", "Apr", "May", "Jun", "Jul"];

const revenueTrend = months.map((m, i) => ({
  month: m,
  revenue: [980000, 1120000, 1340000, 1580000, 1720000, 1960000][i],
  profit: [310000, 380000, 470000, 590000, 640000, 740000][i],
}));

const kpis = [
  { label: "Total Revenue", value: 1960000, change: 14.2, icon: DollarSign, spark: revenueTrend.map(d => ({ v: d.revenue })) },
  { label: "MRR", value: 1650000, change: 9.8, icon: Activity, spark: revenueTrend.map(d => ({ v: d.revenue * 0.85 })) },
  { label: "Gross Profit", value: 1420000, change: 12.1, icon: TrendingUp, spark: revenueTrend.map(d => ({ v: d.revenue * 0.72 })) },
  { label: "Net Profit", value: 740000, change: 15.6, icon: PiggyBank, spark: revenueTrend.map(d => ({ v: d.profit })) },
  { label: "Cash Balance", value: 2140000, change: 6.3, icon: Wallet, spark: revenueTrend.map(d => ({ v: d.profit * 2.8 })) },
  { label: "Outstanding Invoices", value: 385000, change: -8.4, icon: FileText, spark: revenueTrend.map(d => ({ v: d.revenue * 0.15 })) },
  { label: "Active Clients", value: 7, change: 40, icon: Users, isCount: true, spark: [{v:3},{v:4},{v:4},{v:5},{v:6},{v:7}] },
  { label: "Revenue Growth", value: 14.2, change: 3.1, icon: Growth, isPct: true, spark: revenueTrend.map(d => ({ v: d.revenue })) },
  { label: "Profit Margin", value: 37.8, change: 2.4, icon: Percent, isPct: true, spark: revenueTrend.map(d => ({ v: d.profit / d.revenue })) },
  { label: "Burn Rate", value: 680000, change: -4.2, icon: TrendingDown, spark: revenueTrend.map(d => ({ v: d.revenue - d.profit })) },
  { label: "Runway", value: 8.4, change: 1.2, icon: Clock, isMonths: true, spark: [{v:5},{v:6},{v:6.5},{v:7.2},{v:7.9},{v:8.4}] },
  { label: "Customer LTV", value: 1450000, change: 5.8, icon: Target, spark: [{v:1.1},{v:1.2},{v:1.25},{v:1.35},{v:1.4},{v:1.45}] },
  { label: "CAC", value: 62000, change: -11.3, icon: CreditCard, spark: [{v:88},{v:79},{v:74},{v:70},{v:65},{v:62}] },
];

const revenueByService = [
  { name: "Lead Generation", revenue: 980000, clients: 4, acv: 245000, mrr: 730000 },
  { name: "Meta Ads Management", revenue: 540000, clients: 3, acv: 180000, mrr: 420000 },
  { name: "AI Automation", revenue: 260000, clients: 2, acv: 130000, mrr: 260000 },
  { name: "CRM Setup", revenue: 120000, clients: 2, acv: 60000, mrr: 0 },
  { name: "Consulting", revenue: 60000, clients: 1, acv: 60000, mrr: 0 },
];

const expenseCategories = [
  { name: "Marketing", value: 420000, items: [{n:"Meta Ads", v: 380000},{n:"Google Ads", v: 40000}] },
  { name: "Software", value: 165000, items: [{n:"OpenAI", v: 45000},{n:"Claude", v: 20000},{n:"Make", v: 35000},{n:"Airtable", v: 15000},{n:"Apollo", v: 18000},{n:"GoHighLevel", v: 22000},{n:"Domains", v: 4000},{n:"Hosting", v: 6000}] },
  { name: "Operations", value: 310000, items: [{n:"Salaries", v: 200000},{n:"Freelancers", v: 60000},{n:"Internet", v: 15000},{n:"Electricity", v: 20000},{n:"Fuel", v: 10000},{n:"Transport", v: 5000}] },
  { name: "Office", value: 90000, items: [{n:"Rent", v: 70000},{n:"Equipment", v: 20000}] },
  { name: "Personal Withdrawals", value: 235000, items: [{n:"Personal (10% split)", v: 235000}] },
];

const cashFlowMonthly = months.map((m, i) => ({
  month: m,
  in: [1050000, 1180000, 1400000, 1640000, 1780000, 2020000][i],
  out: [740000, 800000, 870000, 990000, 1080000, 1220000][i],
}));

const clients = [
  { name: "Bamidele Adewale", plan: "Starter Retainer", fee: 250000, status: "Paid", paid: "2026-07-01", due: "2026-08-01", outstanding: 0, last: "2026-07-01" },
  { name: "Chioma Realty Group", plan: "Growth Retainer", fee: 500000, status: "Pending", paid: "—", due: "2026-07-20", outstanding: 500000, last: "2026-06-01" },
  { name: "Okafor Estates", plan: "Starter Retainer", fee: 250000, status: "Overdue", paid: "—", due: "2026-07-05", outstanding: 250000, last: "2026-05-28" },
  { name: "PrimeLand Advisory", plan: "Premium Retainer", fee: 900000, status: "Paid", paid: "2026-07-03", due: "2026-08-03", outstanding: 0, last: "2026-07-03" },
  { name: "Segun Properties", plan: "Starter Retainer", fee: 250000, status: "Paid", paid: "2026-06-29", due: "2026-07-29", outstanding: 0, last: "2026-06-29" },
  { name: "Lekki Homes Ltd", plan: "Growth Retainer", fee: 500000, status: "Draft", paid: "—", due: "—", outstanding: 0, last: "—" },
  { name: "Adaeze & Co Realty", plan: "Starter Retainer", fee: 250000, status: "Paid", paid: "2026-07-10", due: "2026-08-10", outstanding: 0, last: "2026-07-10" },
];

const goals = [
  { label: "Revenue Goal", target: 3000000, current: 1960000, forecast: "Sep 2026" },
  { label: "Profit Goal", target: 1200000, current: 740000, forecast: "Oct 2026" },
  { label: "Cash Reserve Goal", target: 5000000, current: 2140000, forecast: "Jan 2027" },
  { label: "Client Goal", target: 12, current: 7, forecast: "Nov 2026", isCount: true },
  { label: "MRR Goal", target: 2500000, current: 1650000, forecast: "Sep 2026" },
];

const healthRatios = [
  { label: "Gross Margin", value: 72.4, good: true },
  { label: "Net Margin", value: 37.8, good: true },
  { label: "Operating Margin", value: 41.2, good: true },
  { label: "Burn Rate", value: 680000, isCurrency: true, good: true },
  { label: "Runway", value: 8.4, isMonths: true, good: true },
  { label: "Quick Ratio", value: 1.8, good: true },
  { label: "Current Ratio", value: 2.3, good: true },
  { label: "Revenue Growth", value: 14.2, isPct: true, good: true },
  { label: "Expense Growth", value: 8.9, isPct: true, good: true },
];

const invoiceSummary = { paid: 5, pending: 1, overdue: 1, draft: 1, outstanding: 750000, avgDays: 6.2 };

const savings = [
  { name: "Emergency Fund", value: 420000, target: 1000000 },
  { name: "Business Savings", value: 680000, target: 1500000 },
  { name: "Marketing Reserve", value: 260000, target: 500000 },
  { name: "Equipment Fund", value: 90000, target: 300000 },
  { name: "Investment Fund", value: 150000, target: 1000000 },
  { name: "Tax Reserve", value: 310000, target: 600000 },
];

const forecast = [
  { month: "Aug", revenue: 2180000, profit: 830000 },
  { month: "Sep", revenue: 2420000, profit: 940000 },
  { month: "Oct", revenue: 2650000, profit: 1050000 },
];

const alerts = [
  { type: "overdue", text: "Okafor Estates invoice is 12 days overdue — ₦250,000", severity: "high" },
  { type: "cash", text: "Marketing Reserve is below target threshold", severity: "medium" },
  { type: "goal", text: "MRR Goal 66% complete — on pace for September", severity: "low" },
  { type: "expense", text: "Meta Ads spend up 18% vs last month", severity: "medium" },
  { type: "renewal", text: "GoHighLevel subscription renews in 3 days — ₦22,000", severity: "low" },
];

const sales = {
  leads: 312, qualified: 148, appointments: 41, closed: 7,
  revenue: 1960000, avgDeal: 280000, closeRate: 17.1, conversionRate: 47.4,
  cac: 62000, ltv: 1450000,
};

/* ---------------------------------------------------------
   PRIMITIVES
--------------------------------------------------------- */

function Card({ children, style, className = "" }) {
  return (
    <div
      className={className}
      style={{
        background: `linear-gradient(160deg, ${COLORS.surface} 0%, #10141F 100%)`,
        border: `1px solid ${COLORS.border}`,
        borderRadius: 16,
        padding: 20,
        ...style,
      }}
    >
      {children}
    </div>
  );
}

function SectionTitle({ icon: Icon, title, sub, id }) {
  return (
    <div id={id} style={{ display: "flex", alignItems: "center", gap: 10, marginBottom: 16, scrollMarginTop: 90 }}>
      <div style={{ width: 32, height: 32, borderRadius: 10, background: COLORS.surface2, display: "flex", alignItems: "center", justifyContent: "center", border: `1px solid ${COLORS.border}` }}>
        <Icon size={16} color={COLORS.gold} />
      </div>
      <div>
        <div style={{ fontFamily: "'Space Grotesk',sans-serif", fontWeight: 600, fontSize: 16, color: COLORS.text }}>{title}</div>
        {sub && <div style={{ fontSize: 12, color: COLORS.muted }}>{sub}</div>}
      </div>
    </div>
  );
}

function Sparkline({ data, positive }) {
  return (
    <ResponsiveContainer width="100%" height={36}>
      <AreaChart data={data}>
        <defs>
          <linearGradient id={`spark-${positive ? "up" : "down"}`} x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stopColor={positive ? COLORS.gold : COLORS.rose} stopOpacity={0.4} />
            <stop offset="100%" stopColor={positive ? COLORS.gold : COLORS.rose} stopOpacity={0} />
          </linearGradient>
        </defs>
        <Area type="monotone" dataKey="v" stroke={positive ? COLORS.gold : COLORS.rose} strokeWidth={1.5} fill={`url(#spark-${positive ? "up" : "down"})`} />
      </AreaChart>
    </ResponsiveContainer>
  );
}

function StatusBadge({ status }) {
  const map = {
    Paid: { bg: "rgba(46,213,115,0.12)", fg: "#4ADE80" },
    Pending: { bg: "rgba(227,179,65,0.12)", fg: COLORS.gold },
    Overdue: { bg: "rgba(229,72,77,0.12)", fg: COLORS.rose },
    Draft: { bg: "rgba(139,127,232,0.12)", fg: "#8B7FE8" },
  };
  const s = map[status] || map.Draft;
  return (
    <span style={{ fontSize: 11, fontFamily: "'JetBrains Mono',monospace", fontWeight: 500, padding: "3px 9px", borderRadius: 999, background: s.bg, color: s.fg, whiteSpace: "nowrap" }}>
      {status}
    </span>
  );
}

/* ---------------------------------------------------------
   MAIN APP
--------------------------------------------------------- */

const navItems = [
  { id: "overview", label: "Overview", icon: LayoutGrid },
  { id: "revenue", label: "Revenue", icon: TrendingUp },
  { id: "expenses", label: "Expenses", icon: PieIcon },
  { id: "cashflow", label: "Cash Flow", icon: Activity },
  { id: "clients", label: "Clients", icon: Building2 },
  { id: "sales", label: "Sales", icon: Target },
  { id: "goals", label: "Goals", icon: Compass },
  { id: "health", label: "Financial Health", icon: CheckCircle2 },
  { id: "invoices", label: "Invoices", icon: FileText },
  { id: "savings", label: "Savings", icon: PiggyBank },
  { id: "forecast", label: "Forecast", icon: TrendingUp },
  { id: "alerts", label: "Alerts", icon: Bell },
];

export default function KringstarAtlas() {
  const [currency, setCurrency] = useState("NGN");
  const [cashFlowView, setCashFlowView] = useState("Monthly");
  const [search, setSearch] = useState("");
  const [statusFilter, setStatusFilter] = useState("All");
  const [sortKey, setSortKey] = useState("name");
  const [page, setPage] = useState(1);
  const pageSize = 5;

  const healthScore = 78; // demo composite score
  const healthColor = healthScore > 70 ? COLORS.gold : healthScore > 45 ? "#E3A341" : COLORS.rose;

  const filteredClients = useMemo(() => {
    let list = clients.filter(c => c.name.toLowerCase().includes(search.toLowerCase()));
    if (statusFilter !== "All") list = list.filter(c => c.status === statusFilter);
    list = [...list].sort((a, b) => {
      if (sortKey === "fee") return b.fee - a.fee;
      if (sortKey === "outstanding") return b.outstanding - a.outstanding;
      return a.name.localeCompare(b.name);
    });
    return list;
  }, [search, statusFilter, sortKey]);

  const totalPages = Math.max(1, Math.ceil(filteredClients.length / pageSize));
  const pagedClients = filteredClients.slice((page - 1) * pageSize, page * pageSize);

  const scrollTo = (id) => {
    document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
  };

  return (
    <div style={{ background: COLORS.base, minHeight: "100vh", fontFamily: "'Inter',sans-serif", color: COLORS.text, display: "flex", position: "relative" }}>
      <style>{fonts}{`
        * { box-sizing: border-box; }
        ::-webkit-scrollbar { width: 8px; height: 8px; }
        ::-webkit-scrollbar-thumb { background: ${COLORS.surface2}; border-radius: 8px; }
        .tabular { font-variant-numeric: tabular-nums; }
        .hoverCard { transition: transform .18s ease, border-color .18s ease; }
        .hoverCard:hover { transform: translateY(-2px); border-color: rgba(227,179,65,0.35) !important; }
        .navBtn { transition: background .15s ease, color .15s ease; }
        .navBtn:hover { background: ${COLORS.surface2}; }
        input, select { outline: none; }
      `}</style>

      {/* Signature vitals pulse */}
      <div style={{
        position: "fixed", left: 0, top: 0, bottom: 0, width: 4, zIndex: 50,
        background: `linear-gradient(180deg, ${healthColor}, transparent 140%)`,
        boxShadow: `0 0 16px ${healthColor}66`,
      }} />

      {/* Sidebar */}
      <aside style={{ width: 220, flexShrink: 0, borderRight: `1px solid ${COLORS.border}`, padding: "24px 14px", position: "sticky", top: 0, height: "100vh", display: "flex", flexDirection: "column", gap: 22 }}>
        <div style={{ display: "flex", alignItems: "center", gap: 9, paddingLeft: 6 }}>
          <Compass size={20} color={COLORS.gold} />
          <div style={{ fontFamily: "'Space Grotesk',sans-serif", fontWeight: 700, fontSize: 15 }}>Kringstar Atlas</div>
        </div>
        <nav style={{ display: "flex", flexDirection: "column", gap: 2 }}>
          {navItems.map(item => (
            <button key={item.id} onClick={() => scrollTo(item.id)} className="navBtn"
              style={{ display: "flex", alignItems: "center", gap: 10, padding: "9px 10px", borderRadius: 9, background: "transparent", border: "none", color: COLORS.muted, fontSize: 13, cursor: "pointer", textAlign: "left" }}>
              <item.icon size={15} />
              {item.label}
            </button>
          ))}
        </nav>
        <div style={{ marginTop: "auto", padding: 12, borderRadius: 12, background: COLORS.surface2, border: `1px solid ${COLORS.border}` }}>
          <div style={{ fontSize: 11, color: COLORS.muted, marginBottom: 6 }}>Atlas Health</div>
          <div style={{ display: "flex", alignItems: "baseline", gap: 6 }}>
            <span style={{ fontFamily: "'JetBrains Mono',monospace", fontSize: 20, fontWeight: 600, color: healthColor }}>{healthScore}</span>
            <span style={{ fontSize: 11, color: COLORS.muted }}>/ 100</span>
          </div>
          <div style={{ height: 4, borderRadius: 4, background: "rgba(255,255,255,0.06)", marginTop: 8, overflow: "hidden" }}>
            <div style={{ height: "100%", width: `${healthScore}%`, background: healthColor, borderRadius: 4 }} />
          </div>
        </div>
      </aside>

      {/* Main */}
      <main style={{ flex: 1, minWidth: 0 }}>
        {/* Topbar */}
        <div style={{ position: "sticky", top: 0, zIndex: 40, backdropFilter: "blur(12px)", background: "rgba(11,15,23,0.85)", borderBottom: `1px solid ${COLORS.border}`, padding: "16px 28px", display: "flex", alignItems: "center", justifyContent: "space-between", gap: 16, flexWrap: "wrap" }}>
          <div>
            <div style={{ fontFamily: "'Space Grotesk',sans-serif", fontWeight: 600, fontSize: 18 }}>Financial Overview</div>
            <div style={{ fontSize: 12, color: COLORS.muted }}>Feb – Jul 2026 · updated moments ago</div>
          </div>
          <div style={{ display: "flex", gap: 8, alignItems: "center", flexWrap: "wrap" }}>
            <div style={{ display: "flex", alignItems: "center", gap: 6, background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 9, padding: "7px 11px", fontSize: 12, color: COLORS.muted }}>
              <Filter size={13} /> Last 6 months <ChevronDown size={13} />
            </div>
            <select value={currency} onChange={e => setCurrency(e.target.value)} style={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 9, padding: "7px 11px", fontSize: 12, color: COLORS.text }}>
              <option value="NGN">₦ NGN</option>
              <option value="USD">$ USD</option>
              <option value="GBP">£ GBP</option>
              <option value="EUR">€ EUR</option>
            </select>
            {["PDF", "CSV", "Excel"].map(f => (
              <button key={f} style={{ display: "flex", alignItems: "center", gap: 6, background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 9, padding: "7px 11px", fontSize: 12, color: COLORS.text, cursor: "pointer" }}>
                <Download size={13} /> {f}
              </button>
            ))}
          </div>
        </div>

        <div style={{ padding: "28px 28px 80px" }}>

          {/* KPI GRID */}
          <div id="overview" style={{ scrollMarginTop: 90 }}>
            <SectionTitle icon={LayoutGrid} title="Key Metrics" sub="Business health at a glance" />
            <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit,minmax(220px,1fr))", gap: 14 }}>
              {kpis.map((k, i) => {
                const positive = k.change >= 0;
                return (
                  <Card key={i} className="hoverCard">
                    <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-start" }}>
                      <div style={{ width: 30, height: 30, borderRadius: 8, background: COLORS.surface2, display: "flex", alignItems: "center", justifyContent: "center" }}>
                        <k.icon size={14} color={COLORS.gold} />
                      </div>
                      <div style={{ display: "flex", alignItems: "center", gap: 3, fontSize: 11, color: positive ? "#4ADE80" : COLORS.rose, fontFamily: "'JetBrains Mono',monospace" }}>
                        {positive ? <ArrowUpRight size={12} /> : <ArrowDownRight size={12} />}
                        {Math.abs(k.change)}%
                      </div>
                    </div>
                    <div style={{ marginTop: 12, fontSize: 12, color: COLORS.muted }}>{k.label}</div>
                    <div className="tabular" style={{ fontFamily: "'Space Grotesk',sans-serif", fontSize: 21, fontWeight: 600, marginTop: 2 }}>
                      {k.isPct ? `${k.value}%` : k.isMonths ? `${k.value} mo` : k.isCount ? k.value : naira(k.value, true)}
                    </div>
                    <div style={{ marginTop: 8 }}><Sparkline data={k.spark} positive={positive} /></div>
                  </Card>
                );
              })}
            </div>
          </div>

          {/* REVENUE */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="revenue" icon={TrendingUp} title="Revenue by Service" sub="Year-to-date breakdown" />
            <div style={{ display: "grid", gridTemplateColumns: "1.4fr 1fr", gap: 14 }}>
              <Card>
                <ResponsiveContainer width="100%" height={260}>
                  <BarChart data={revenueByService} layout="vertical" margin={{ left: 10 }}>
                    <CartesianGrid strokeDasharray="3 3" stroke={COLORS.border} horizontal={false} />
                    <XAxis type="number" tick={{ fill: COLORS.muted, fontSize: 11 }} tickFormatter={v => naira(v, true)} axisLine={false} tickLine={false} />
                    <YAxis type="category" dataKey="name" tick={{ fill: COLORS.text, fontSize: 11 }} width={130} axisLine={false} tickLine={false} />
                    <Tooltip contentStyle={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 10, fontSize: 12 }} formatter={v => naira(v)} />
                    <Bar dataKey="revenue" fill={COLORS.gold} radius={[0, 6, 6, 0]} barSize={18} />
                  </BarChart>
                </ResponsiveContainer>
              </Card>
              <Card>
                <ResponsiveContainer width="100%" height={220}>
                  <PieChart>
                    <Pie data={revenueByService} dataKey="revenue" nameKey="name" innerRadius={55} outerRadius={85} paddingAngle={3}>
                      {revenueByService.map((_, i) => <Cell key={i} fill={PIE_COLORS[i % PIE_COLORS.length]} />)}
                    </Pie>
                    <Tooltip contentStyle={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 10, fontSize: 12 }} formatter={v => naira(v)} />
                  </PieChart>
                </ResponsiveContainer>
                <div style={{ display: "flex", flexDirection: "column", gap: 6, marginTop: 4 }}>
                  {revenueByService.map((s, i) => (
                    <div key={i} style={{ display: "flex", alignItems: "center", gap: 7, fontSize: 11, color: COLORS.muted }}>
                      <span style={{ width: 8, height: 8, borderRadius: 3, background: PIE_COLORS[i % PIE_COLORS.length] }} />
                      {s.name}
                    </div>
                  ))}
                </div>
              </Card>
            </div>
            <Card style={{ marginTop: 14, padding: 0, overflow: "hidden" }}>
              <table style={{ width: "100%", borderCollapse: "collapse", fontSize: 12 }}>
                <thead>
                  <tr style={{ background: COLORS.surface2, color: COLORS.muted, textAlign: "left" }}>
                    {["Service", "Revenue", "Clients", "Avg Contract", "MRR"].map(h => <th key={h} style={{ padding: "10px 16px", fontWeight: 500 }}>{h}</th>)}
                  </tr>
                </thead>
                <tbody>
                  {revenueByService.map((s, i) => (
                    <tr key={i} style={{ borderTop: `1px solid ${COLORS.border}` }}>
                      <td style={{ padding: "10px 16px" }}>{s.name}</td>
                      <td className="tabular" style={{ padding: "10px 16px" }}>{naira(s.revenue)}</td>
                      <td className="tabular" style={{ padding: "10px 16px" }}>{s.clients}</td>
                      <td className="tabular" style={{ padding: "10px 16px" }}>{naira(s.acv)}</td>
                      <td className="tabular" style={{ padding: "10px 16px" }}>{s.mrr ? naira(s.mrr) : "—"}</td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </Card>
          </div>

          {/* EXPENSES */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="expenses" icon={PieIcon} title="Expenses" sub="By category" />
            <div style={{ display: "grid", gridTemplateColumns: "1fr 1.4fr", gap: 14 }}>
              <Card>
                <ResponsiveContainer width="100%" height={240}>
                  <PieChart>
                    <Pie data={expenseCategories} dataKey="value" nameKey="name" innerRadius={60} outerRadius={90} paddingAngle={3}>
                      {expenseCategories.map((_, i) => <Cell key={i} fill={PIE_COLORS[i % PIE_COLORS.length]} />)}
                    </Pie>
                    <Tooltip contentStyle={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 10, fontSize: 12 }} formatter={v => naira(v)} />
                  </PieChart>
                </ResponsiveContainer>
              </Card>
              <div style={{ display: "flex", flexDirection: "column", gap: 10 }}>
                {expenseCategories.map((cat, i) => {
                  const total = expenseCategories.reduce((a, c) => a + c.value, 0);
                  const pct = ((cat.value / total) * 100).toFixed(1);
                  return (
                    <Card key={i} style={{ padding: 14 }}>
                      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center" }}>
                        <div style={{ display: "flex", alignItems: "center", gap: 8 }}>
                          <span style={{ width: 8, height: 8, borderRadius: 3, background: PIE_COLORS[i % PIE_COLORS.length] }} />
                          <span style={{ fontSize: 13, fontWeight: 500 }}>{cat.name}</span>
                        </div>
                        <div className="tabular" style={{ fontSize: 13, fontFamily: "'JetBrains Mono',monospace" }}>{naira(cat.value)} <span style={{ color: COLORS.muted }}>({pct}%)</span></div>
                      </div>
                      <div style={{ height: 4, borderRadius: 4, background: "rgba(255,255,255,0.06)", marginTop: 8 }}>
                        <div style={{ height: "100%", width: `${pct}%`, background: PIE_COLORS[i % PIE_COLORS.length], borderRadius: 4 }} />
                      </div>
                    </Card>
                  );
                })}
              </div>
            </div>
          </div>

          {/* CASH FLOW */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="cashflow" icon={Activity} title="Cash Flow" sub="In vs out over time" />
            <Card>
              <div style={{ display: "flex", gap: 6, marginBottom: 12 }}>
                {["Daily", "Weekly", "Monthly", "Quarterly"].map(v => (
                  <button key={v} onClick={() => setCashFlowView(v)}
                    style={{ fontSize: 11, padding: "5px 11px", borderRadius: 999, cursor: "pointer", border: `1px solid ${COLORS.border}`, background: cashFlowView === v ? COLORS.gold : "transparent", color: cashFlowView === v ? "#1A1400" : COLORS.muted, fontWeight: 500 }}>
                    {v}
                  </button>
                ))}
              </div>
              <ResponsiveContainer width="100%" height={260}>
                <AreaChart data={cashFlowMonthly}>
                  <defs>
                    <linearGradient id="inGrad" x1="0" y1="0" x2="0" y2="1"><stop offset="0%" stopColor={COLORS.teal} stopOpacity={0.35} /><stop offset="100%" stopColor={COLORS.teal} stopOpacity={0} /></linearGradient>
                    <linearGradient id="outGrad" x1="0" y1="0" x2="0" y2="1"><stop offset="0%" stopColor={COLORS.rose} stopOpacity={0.25} /><stop offset="100%" stopColor={COLORS.rose} stopOpacity={0} /></linearGradient>
                  </defs>
                  <CartesianGrid strokeDasharray="3 3" stroke={COLORS.border} vertical={false} />
                  <XAxis dataKey="month" tick={{ fill: COLORS.muted, fontSize: 11 }} axisLine={false} tickLine={false} />
                  <YAxis tick={{ fill: COLORS.muted, fontSize: 11 }} tickFormatter={v => naira(v, true)} axisLine={false} tickLine={false} />
                  <Tooltip contentStyle={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 10, fontSize: 12 }} formatter={v => naira(v)} />
                  <Area type="monotone" dataKey="in" stroke={COLORS.teal} strokeWidth={2} fill="url(#inGrad)" name="Cash In" />
                  <Area type="monotone" dataKey="out" stroke={COLORS.rose} strokeWidth={2} fill="url(#outGrad)" name="Cash Out" />
                </AreaChart>
              </ResponsiveContainer>
              <div style={{ display: "flex", gap: 20, marginTop: 8, fontSize: 12, color: COLORS.muted }}>
                <div><span style={{ color: COLORS.teal }}>●</span> Cash In</div>
                <div><span style={{ color: COLORS.rose }}>●</span> Cash Out</div>
              </div>
            </Card>
          </div>

          {/* CLIENTS */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="clients" icon={Building2} title="Client Revenue" sub={`${filteredClients.length} of ${clients.length} clients`} />
            <Card style={{ padding: 0, overflow: "hidden" }}>
              <div style={{ display: "flex", gap: 8, padding: 14, borderBottom: `1px solid ${COLORS.border}`, flexWrap: "wrap" }}>
                <div style={{ display: "flex", alignItems: "center", gap: 7, background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 9, padding: "7px 11px", flex: 1, minWidth: 180 }}>
                  <Search size={13} color={COLORS.muted} />
                  <input placeholder="Search clients…" value={search} onChange={e => { setSearch(e.target.value); setPage(1); }}
                    style={{ background: "transparent", border: "none", color: COLORS.text, fontSize: 12, width: "100%" }} />
                </div>
                <select value={statusFilter} onChange={e => { setStatusFilter(e.target.value); setPage(1); }}
                  style={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 9, padding: "7px 11px", fontSize: 12, color: COLORS.text }}>
                  {["All", "Paid", "Pending", "Overdue", "Draft"].map(s => <option key={s}>{s}</option>)}
                </select>
                <select value={sortKey} onChange={e => setSortKey(e.target.value)}
                  style={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 9, padding: "7px 11px", fontSize: 12, color: COLORS.text }}>
                  <option value="name">Sort: Name</option>
                  <option value="fee">Sort: Fee</option>
                  <option value="outstanding">Sort: Outstanding</option>
                </select>
              </div>
              <div style={{ overflowX: "auto" }}>
                <table style={{ width: "100%", borderCollapse: "collapse", fontSize: 12, minWidth: 760 }}>
                  <thead>
                    <tr style={{ background: COLORS.surface2, color: COLORS.muted, textAlign: "left" }}>
                      {["Client", "Plan", "Fee", "Status", "Due Date", "Outstanding", "Last Payment", ""].map(h => <th key={h} style={{ padding: "10px 16px", fontWeight: 500 }}>{h}</th>)}
                    </tr>
                  </thead>
                  <tbody>
                    {pagedClients.map((c, i) => (
                      <tr key={i} style={{ borderTop: `1px solid ${COLORS.border}` }}>
                        <td style={{ padding: "12px 16px", fontWeight: 500 }}>{c.name}</td>
                        <td style={{ padding: "12px 16px", color: COLORS.muted }}>{c.plan}</td>
                        <td className="tabular" style={{ padding: "12px 16px" }}>{naira(c.fee)}</td>
                        <td style={{ padding: "12px 16px" }}><StatusBadge status={c.status} /></td>
                        <td className="tabular" style={{ padding: "12px 16px", color: COLORS.muted }}>{c.due}</td>
                        <td className="tabular" style={{ padding: "12px 16px", color: c.outstanding ? COLORS.rose : COLORS.muted }}>{c.outstanding ? naira(c.outstanding) : "—"}</td>
                        <td className="tabular" style={{ padding: "12px 16px", color: COLORS.muted }}>{c.last}</td>
                        <td style={{ padding: "12px 16px" }}><button style={{ background: "none", border: "none", color: COLORS.gold, fontSize: 12, cursor: "pointer" }}>View</button></td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>
              <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", padding: 14 }}>
                <span style={{ fontSize: 11, color: COLORS.muted }}>Page {page} of {totalPages}</span>
                <div style={{ display: "flex", gap: 6 }}>
                  <button onClick={() => setPage(p => Math.max(1, p - 1))} style={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 8, padding: 6, cursor: "pointer", color: COLORS.text }}><ChevronLeft size={13} /></button>
                  <button onClick={() => setPage(p => Math.min(totalPages, p + 1))} style={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 8, padding: 6, cursor: "pointer", color: COLORS.text }}><ChevronRight size={13} /></button>
                </div>
              </div>
            </Card>
          </div>

          {/* SALES METRICS */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="sales" icon={Target} title="Sales Metrics" sub="Funnel performance" />
            <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit,minmax(160px,1fr))", gap: 12 }}>
              {[
                { l: "Leads", v: sales.leads }, { l: "Qualified Leads", v: sales.qualified },
                { l: "Appointments", v: sales.appointments }, { l: "Deals Closed", v: sales.closed },
                { l: "Revenue", v: naira(sales.revenue, true) }, { l: "Avg Deal Size", v: naira(sales.avgDeal, true) },
                { l: "Close Rate", v: `${sales.closeRate}%` }, { l: "Conversion Rate", v: `${sales.conversionRate}%` },
                { l: "CAC", v: naira(sales.cac, true) }, { l: "LTV", v: naira(sales.ltv, true) },
                { l: "LTV : CAC", v: `${(sales.ltv / sales.cac).toFixed(1)}x` },
              ].map((s, i) => (
                <Card key={i} className="hoverCard" style={{ padding: 14 }}>
                  <div style={{ fontSize: 11, color: COLORS.muted }}>{s.l}</div>
                  <div className="tabular" style={{ fontFamily: "'Space Grotesk',sans-serif", fontSize: 18, fontWeight: 600, marginTop: 4 }}>{s.v}</div>
                </Card>
              ))}
            </div>
          </div>

          {/* GOALS */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="goals" icon={Compass} title="Goals" sub="Progress toward targets" />
            <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit,minmax(220px,1fr))", gap: 14 }}>
              {goals.map((g, i) => {
                const pct = Math.min(100, (g.current / g.target) * 100);
                return (
                  <Card key={i} className="hoverCard">
                    <div style={{ fontSize: 12, color: COLORS.muted }}>{g.label}</div>
                    <div className="tabular" style={{ fontFamily: "'Space Grotesk',sans-serif", fontSize: 19, fontWeight: 600, marginTop: 4 }}>
                      {g.isCount ? g.current : naira(g.current, true)} <span style={{ fontSize: 12, color: COLORS.muted, fontFamily: "'Inter',sans-serif" }}>/ {g.isCount ? g.target : naira(g.target, true)}</span>
                    </div>
                    <div style={{ height: 6, borderRadius: 4, background: "rgba(255,255,255,0.06)", marginTop: 10, overflow: "hidden" }}>
                      <div style={{ height: "100%", width: `${pct}%`, background: `linear-gradient(90deg, ${COLORS.gold}, ${COLORS.teal})`, borderRadius: 4 }} />
                    </div>
                    <div style={{ display: "flex", justifyContent: "space-between", marginTop: 8, fontSize: 11, color: COLORS.muted }}>
                      <span>{pct.toFixed(0)}% complete</span>
                      <span>Forecast: {g.forecast}</span>
                    </div>
                  </Card>
                );
              })}
            </div>
          </div>

          {/* FINANCIAL HEALTH */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="health" icon={CheckCircle2} title="Financial Health" sub="Ratios & margins" />
            <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit,minmax(160px,1fr))", gap: 12 }}>
              {healthRatios.map((r, i) => (
                <Card key={i} style={{ padding: 14 }}>
                  <div style={{ fontSize: 11, color: COLORS.muted }}>{r.label}</div>
                  <div className="tabular" style={{ fontFamily: "'Space Grotesk',sans-serif", fontSize: 18, fontWeight: 600, marginTop: 4, color: r.good ? "#4ADE80" : COLORS.rose }}>
                    {r.isCurrency ? naira(r.value, true) : r.isMonths ? `${r.value} mo` : r.isPct ? `${r.value}%` : r.value}
                  </div>
                </Card>
              ))}
            </div>
          </div>

          {/* INVOICES */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="invoices" icon={FileText} title="Invoices" sub="Status breakdown" />
            <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit,minmax(150px,1fr))", gap: 12 }}>
              <Card style={{ padding: 14 }}><StatusBadge status="Paid" /><div className="tabular" style={{ fontSize: 22, fontWeight: 600, marginTop: 10 }}>{invoiceSummary.paid}</div></Card>
              <Card style={{ padding: 14 }}><StatusBadge status="Pending" /><div className="tabular" style={{ fontSize: 22, fontWeight: 600, marginTop: 10 }}>{invoiceSummary.pending}</div></Card>
              <Card style={{ padding: 14 }}><StatusBadge status="Overdue" /><div className="tabular" style={{ fontSize: 22, fontWeight: 600, marginTop: 10 }}>{invoiceSummary.overdue}</div></Card>
              <Card style={{ padding: 14 }}><StatusBadge status="Draft" /><div className="tabular" style={{ fontSize: 22, fontWeight: 600, marginTop: 10 }}>{invoiceSummary.draft}</div></Card>
              <Card style={{ padding: 14 }}><div style={{ fontSize: 11, color: COLORS.muted }}>Total Outstanding</div><div className="tabular" style={{ fontSize: 18, fontWeight: 600, marginTop: 8, color: COLORS.rose }}>{naira(invoiceSummary.outstanding)}</div></Card>
              <Card style={{ padding: 14 }}><div style={{ fontSize: 11, color: COLORS.muted }}>Avg Payment Time</div><div className="tabular" style={{ fontSize: 18, fontWeight: 600, marginTop: 8 }}>{invoiceSummary.avgDays} days</div></Card>
            </div>
          </div>

          {/* SAVINGS */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="savings" icon={PiggyBank} title="Savings" sub="Reserve funds" />
            <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit,minmax(200px,1fr))", gap: 14 }}>
              {savings.map((s, i) => {
                const pct = Math.min(100, (s.value / s.target) * 100);
                return (
                  <Card key={i} style={{ padding: 14 }}>
                    <div style={{ fontSize: 12, color: COLORS.muted }}>{s.name}</div>
                    <div className="tabular" style={{ fontSize: 17, fontWeight: 600, marginTop: 4 }}>{naira(s.value, true)} <span style={{ fontSize: 11, color: COLORS.muted }}>/ {naira(s.target, true)}</span></div>
                    <div style={{ height: 5, borderRadius: 4, background: "rgba(255,255,255,0.06)", marginTop: 8 }}>
                      <div style={{ height: "100%", width: `${pct}%`, background: COLORS.teal, borderRadius: 4 }} />
                    </div>
                  </Card>
                );
              })}
            </div>
          </div>

          {/* FORECAST */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="forecast" icon={TrendingUp} title="Forecast" sub="Next 3 months, projected" />
            <Card>
              <ResponsiveContainer width="100%" height={240}>
                <LineChart data={[...revenueTrend.map(d => ({ month: d.month, revenue: d.revenue, profit: d.profit, projected: false })), ...forecast.map(d => ({ ...d, projected: true }))]}>
                  <CartesianGrid strokeDasharray="3 3" stroke={COLORS.border} vertical={false} />
                  <XAxis dataKey="month" tick={{ fill: COLORS.muted, fontSize: 11 }} axisLine={false} tickLine={false} />
                  <YAxis tick={{ fill: COLORS.muted, fontSize: 11 }} tickFormatter={v => naira(v, true)} axisLine={false} tickLine={false} />
                  <Tooltip contentStyle={{ background: COLORS.surface2, border: `1px solid ${COLORS.border}`, borderRadius: 10, fontSize: 12 }} formatter={v => naira(v)} />
                  <Line type="monotone" dataKey="revenue" stroke={COLORS.gold} strokeWidth={2} dot={{ r: 3 }} strokeDasharray="0" />
                  <Line type="monotone" dataKey="profit" stroke={COLORS.teal} strokeWidth={2} dot={{ r: 3 }} />
                </LineChart>
              </ResponsiveContainer>
              <div style={{ fontSize: 11, color: COLORS.muted, marginTop: 6 }}>Aug–Oct values are projected based on current growth trend.</div>
            </Card>
          </div>

          {/* ALERTS */}
          <div style={{ marginTop: 40 }}>
            <SectionTitle id="alerts" icon={Bell} title="Alert Center" sub="Needs your attention" />
            <div style={{ display: "flex", flexDirection: "column", gap: 10 }}>
              {alerts.map((a, i) => {
                const sevColor = a.severity === "high" ? COLORS.rose : a.severity === "medium" ? COLORS.gold : COLORS.teal;
                const Icon = a.severity === "high" ? AlertTriangle : a.severity === "medium" ? Bell : CheckCircle2;
                return (
                  <Card key={i} style={{ padding: 14, display: "flex", alignItems: "center", gap: 12 }}>
                    <div style={{ width: 30, height: 30, borderRadius: 8, background: `${sevColor}1F`, display: "flex", alignItems: "center", justifyContent: "center", flexShrink: 0 }}>
                      <Icon size={14} color={sevColor} />
                    </div>
                    <div style={{ fontSize: 13 }}>{a.text}</div>
                  </Card>
                );
              })}
            </div>
          </div>

        </div>
      </main>
    </div>
  );
}
