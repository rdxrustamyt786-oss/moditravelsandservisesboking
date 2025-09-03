# moditravelsandservisesboking import React, { useMemo, useState } from "react"; import { motion } from "framer-motion"; import { Button } from "@/components/ui/button"; import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"; import { Input } from "@/components/ui/input"; import { Textarea } from "@/components/ui/textarea"; import { Plane, Train, Bus, Building2, IndianRupee, ShieldCheck, Clock, Stars, Phone, Mail, MapPin, Globe2, CreditCard, IdCard, FileBadge, FileCheck2, Link2, FileImage, FilePenLine, FileSearch, FileSpreadsheet, FileSignature, } from "lucide-react";

// ===================== // Modi Travels & Services – Landing Page // Tech: React + Tailwind + shadcn/ui + framer-motion // =====================

const SERVICES = [ { title: "Aadhar Card", icon: IdCard }, { title: "PAN Card", icon: CreditCard }, { title: "Train Ticket", icon: Train }, { title: "Flight Ticket", icon: Plane }, { title: "Voter ID", icon: IdCard }, { title: "Udyam Aadhar", icon: FileBadge }, { title: "Aadhar Card Bank Seeding", icon: Link2 }, { title: "E-Shram Card", icon: FileBadge }, { title: "PAN Finder", icon: FileSearch }, { title: "DL Apply", icon: FileSignature }, { title: "Passport Apply", icon: Globe2 }, { title: "Manual PAN Card", icon: CreditCard }, { title: "PAN Aadhar Link", icon: Link2 }, { title: "Bihar Income + Residence + Caste Certificate", icon: FileCheck2 }, { title: "UP Residence + Income + Caste Certificate", icon: FileCheck2 }, { title: "PF Services", icon: FileSpreadsheet }, { title: "Image Edit Tools Online", icon: FileImage }, { title: "PDF Edit Tools Online", icon: FilePenLine }, // Common travel agency services (keep for completeness) { title: "Bus Booking", icon: Bus }, { title: "Hotel Booking", icon: Building2 }, ];

const PACKAGES = [ { name: "Goa Beach Escape", desc: "3N/4D hotel + flights + breakfast", price: "From ₹12,999", image: "https://images.unsplash.com/photo-1512453979798-5ea266f8880c?q=80&w=1600&auto=format&fit=crop", }, { name: "Kashmir Paradise", desc: "4N/5D houseboat + sightseeing", price: "From ₹16,499", image: "https://images.unsplash.com/photo-1581160854300-4f8c2c9519a0?q=80&w=1600&auto=format&fit=crop", }, { name: "Dubai Highlights", desc: "4N/5D visa + hotel + city tour", price: "From ₹39,999", image: "https://images.unsplash.com/photo-1465414829459-d228b58caf6e?q=80&w=1600&auto=format&fit=crop", }, ];

const Stat = ({ value, label }: { value: string; label: string }) => (

  <div className="text-center">
    <div className="text-3xl font-extrabold tracking-tight">{value}</div>
    <div className="text-xs opacity-70 mt-1">{label}</div>
  </div>
);export default function ModiTravelsLanding() { const [query, setQuery] = useState("");

const filtered = useMemo(() => { const q = query.trim().toLowerCase(); if (!q) return SERVICES; return SERVICES.filter((s) => s.title.toLowerCase().includes(q)); }, [query]);

return ( <div className="min-h-screen bg-gradient-to-b from-white to-slate-50 text-slate-900"> {/* Header */} <header className="sticky top-0 z-50 backdrop-blur supports-[backdrop-filter]:bg-white/70 bg-white/60 border-b"> <div className="mx-auto max-w-6xl px-4 py-3 flex items-center justify-between"> <div className="flex items-center gap-3"> <div className="h-10 w-10 rounded-2xl bg-slate-900 text-white grid place-content-center font-black">M</div> <div> <h1 className="text-lg font-bold leading-tight">Modi Travels & Services</h1> <p className="text-xs opacity-70 -mt-0.5">Your Trusted Travel & Citizen Services Partner</p> </div> </div> <nav className="hidden md:flex items-center gap-6 text-sm"> <a href="#services" className="hover:opacity-80">Services</a> <a href="#packages" className="hover:opacity-80">Packages</a> <a href="#why-us" className="hover:opacity-80">Why Us</a> <a href="#contact" className="hover:opacity-80">Contact</a> </nav> <Button className="rounded-2xl px-5">Book Now</Button> </div> </header>

{/* Hero */}
  <section className="relative">
    <div
      className="absolute inset-0 -z-10"
      style={{
        backgroundImage:
          "url(https://images.unsplash.com/photo-1502920917128-1aa500764cbd?q=80&w=2069&auto=format&fit=crop)",
        backgroundSize: "cover",
        backgroundPosition: "center",
      }}
    />
    <div className="absolute inset-0 -z-10 bg-gradient-to-b from-black/40 via-black/30 to-white" />
    <div className="mx-auto max-w-6xl px-4 py-24 md:py-32 text-white">
      <motion.h2
        initial={{ opacity: 0, y: 20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.6 }}
        className="text-4xl md:text-6xl font-extrabold max-w-3xl leading-tight"
      >
        Discover. Book. Go.
      </motion.h2>
      <motion.p
        initial={{ opacity: 0, y: 20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.7, delay: 0.1 }}
        className="mt-4 md:text-lg max-w-2xl"
      >
        Flights, trains, hotels, bus tickets, and essential government services—everything in one place.
      </motion.p>
      <motion.div
        initial={{ opacity: 0, y: 20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.7, delay: 0.15 }}
        className="mt-8 flex items-center gap-3"
      >
        <Button size="lg" className="rounded-2xl px-7">Plan Your Trip</Button>
        <Button size="lg" variant="secondary" className="rounded-2xl px-7">Get Assistance</Button>
      </motion.div>

      {/* Quick stats */}
      <div className="mt-10 grid grid-cols-3 md:grid-cols-6 gap-6 max-w-3xl">
        <Stat value="24/7" label="Support" />
        <Stat value=">10K" label="Happy Clients" />
        <Stat value="₹₹" label="Best Prices" />
        <Stat value="Fast" label="Instant Booking" />
        <Stat value="Secure" label="Trusted Service" />
        <Stat value="Multi" label="All-in-One" />
      </div>
    </div>
  </section>

  {/* Services */}
  <section id="services" className="mx-auto max-w-6xl px-4 py-16">
    <div className="flex flex-col md:flex-row md:items-end md:justify-between gap-4">
      <div>
        <h3 className="text-2xl md:text-3xl font-bold">Our Services</h3>
        <p className="text-sm opacity-70 mt-1">Travel bookings, ID services, certificates, PF & more</p>
      </div>
      <div className="md:w-80">
        <Input
          placeholder="Search services (e.g., PAN, Passport, PF)"
          value={query}
          onChange={(e) => setQuery(e.target.value)}
          className="rounded-xl"
        />
      </div>
    </div>

    <div className="mt-8 grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4 md:gap-6">
      {filtered.map((s, i) => (
        <motion.div key={s.title} initial={{ opacity: 0, y: 12 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }} transition={{ delay: i * 0.015 }}>
          <Card className="rounded-2xl border border-slate-200 hover:shadow-md transition-shadow h-full">
            <CardHeader className="pb-2">
              <div className="flex items-center gap-3">
                {React.createElement(s.icon, { className: "h-5 w-5" })}
                <CardTitle className="text-base font-semibold leading-tight">{s.title}</CardTitle>
              </div>
            </CardHeader>
            <CardContent className="pt-0">
              <p className="text-xs opacity-70">Quick processing • Expert guidance • Digital/Offline</p>
              <div className="mt-3 flex gap-2">
                <Button size="sm" className="rounded-xl">Apply</Button>
                <Button size="sm" variant="secondary" className="rounded-xl">Know More</Button>
              </div>
            </CardContent>
          </Card>
        </motion.div>
      ))}
    </div>
  </section>

  {/* Why Choose Us */}
  <section id="why-us" className="mx-auto max-w-6xl px-4 pb-4">
    <div className="grid md:grid-cols-4 gap-4 md:gap-6">
      <Card className="rounded-2xl">
        <CardHeader className="pb-2"><CardTitle className="text-lg flex items-center gap-2"><Clock className="h-5 w-5"/>Fast Processing</CardTitle></CardHeader>
        <CardContent className="text-sm opacity-80">Save time with instant ticketing & same-day document services wherever possible.</CardContent>
      </Card>
      <Card className="rounded-2xl">
        <CardHeader className="pb-2"><CardTitle className="text-lg flex items-center gap-2"><IndianRupee className="h-5 w-5"/>Best Prices</CardTitle></CardHeader>
        <CardContent className="text-sm opacity-80">Transparent pricing and seasonal offers for trips & packages.</CardContent>
      </Card>
      <Card className="rounded-2xl">
        <CardHeader className="pb-2"><CardTitle className="text-lg flex items-center gap-2"><ShieldCheck className="h-5 w-5"/>Trusted & Secure</CardTitle></CardHeader>
        <CardContent className="text-sm opacity-80">We follow secure processes for document handling and payments.</CardContent>
      </Card>
      <Card className="rounded-2xl">
        <CardHeader className="pb-2"><CardTitle className="text-lg flex items-center gap-2"><Stars className="h-5 w-5"/>Expert Support</CardTitle></CardHeader>
        <CardContent className="text-sm opacity-80">Dedicated assistance on WhatsApp/Call from enquiry to delivery.</CardContent>
      </Card>
    </div>
  </section>

  {/* Packages */}
  <section id="packages" className="mx-auto max-w-6xl px-4 py-16">
    <div className="flex items-end justify-between">
      <div>
        <h3 className="text-2xl md:text-3xl font-bold">Popular Packages</h3>
        <p className="text-sm opacity-70 mt-1">Hand-picked trips with great value</p>
      </div>
      <Button className="rounded-2xl">View All</Button>
    </div>
    <div className="mt-8 grid md:grid-cols-3 gap-6">
      {PACKAGES.map((p, idx) => (
        <motion.div key={p.name} initial={{ opacity: 0, y: 16 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }} transition={{ delay: idx * 0.05 }}>
          <Card className="overflow-hidden rounded-2xl border-slate-200 hover:shadow-md transition-shadow">
            <div className="h-40 bg-cover bg-center" style={{ backgroundImage: `url(${p.image})` }} />
            <CardHeader className="pb-1">
              <CardTitle className="text-lg">{p.name}</CardTitle>
            </CardHeader>
            <CardContent>
              <p className="text-sm opacity-80">{p.desc}</p>
              <div className="mt-3 flex items-center justify-between">
                <span className="text-sm font-semibold">{p.price}</span>
                <Button size="sm" className="rounded-xl">Book Now</Button>
              </div>
            </CardContent>
          </Card>
        </motion.div>
      ))}
    </div>
  </section>

  {/* Contact */}
  <section id="contact" className="bg-white/70 border-t">
    <div className="mx-auto max-w-6xl px-4 py-16 grid md:grid-cols-2 gap-8">
      <div>
        <h3 className="text-2xl md:text-3xl font-bold">Get in Touch</h3>
        <p className="text-sm opacity-70 mt-1">We usually respond within minutes during working hours.</p>

        <div className="mt-6 space-y-3 text-sm">
          <div className="flex items-center gap-3"><Phone className="h-4 w-4"/><span><strong>Call/WhatsApp:</strong> +91-9767707483</span></div>
          <div className="flex items-center gap-3"><Mail className="h-4 w-4"/><span><strong>Email:</strong> moditravelsandservises@gmail.com</span></div>
          <div className="flex items-center gap-3"><MapPin className="h-4 w-4"/><span><strong>Address:</strong> Shop no. 06, Divya Chetna Apartment, Shivaji Maharaj Chowk, Anand Nagar, Vasai West 401202</span></div>
        </div>

        <div className="mt-6 grid grid-cols-3 gap-4 text-sm">
          <a className="border rounded-xl p-3 text-center hover:bg-slate-50" href="#">Google Map</a>
          <a className="border rounded-xl p-3 text-center hover:bg-slate-50" href="#">WhatsApp</a>
          <a className="border rounded-xl p-3 text-center hover:bg-slate-50" href="#">Facebook</a>
        </div>
      </div>

      <Card className="rounded-2xl">
        <CardHeader className="pb-2"><CardTitle className="text-lg">Quick Enquiry</CardTitle></CardHeader>
        <CardContent className="space-y-3">
          <Input placeholder="Your Name" className="rounded-xl" />
          <Input placeholder="Phone Number" className="rounded-xl" />
          <Input placeholder="Email (optional)" className="rounded-xl" />
          <Textarea placeholder="Tell us your requirement (e.g., Train ticket tomorrow to Delhi, PAN update, etc.)" className="rounded-xl" rows={4} />
          <Button className="w-full rounded-xl">Send Enquiry</Button>
          <p className="text-xs opacity-60">By submitting, you agree to our terms & privacy policy.</p>
        </CardContent>
      </Card>
    </div>
  </section>

