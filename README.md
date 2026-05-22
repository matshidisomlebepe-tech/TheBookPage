import { useState } from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input"; import { motion } from "framer-motion";

export default function GrowthBookSite() { const [email, setEmail] = useState(""); const [subscribed, setSubscribed] = useState(false);

const handleSubscribe = () => { if (!email.includes("@")) return; setSubscribed(true); setEmail(""); };

const handleDownload = () => { alert("Connect this button to your hosted PDF file (Google Drive, AWS, or KDP link)."); };

return ( <div className="min-h-screen bg-white text-gray-900 p-6"> {/* HEADER */} <motion.div initial={{ opacity: 0, y: -20 }} animate={{ opacity: 1, y: 0 }} className="text-center mb-10" > <h1 className="text-5xl font-bold">GROWTH</h1> <p className="text-lg mt-2 italic"> A Journey Through Becoming Who You Are Meant To Be </p> <p className="text-sm text-gray-500">by Matshidiso Lebepe</p> </motion.div>

{/* ABOUT */}
  <div className="grid md:grid-cols-2 gap-6 mb-10">
    <Card className="rounded-2xl shadow-lg">
      <CardContent className="p-6">
        <h2 className="text-xl font-semibold">About the Book</h2>
        <p className="text-gray-700 mt-2">
          A narrative self-help story following a man who slowly realizes
          that his life is changing internally long before anything changes
          externally. It explores identity, silence, discipline, and
          emotional transformation.
        </p>
      </CardContent>
    </Card>

    <Card className="rounded-2xl shadow-lg">
      <CardContent className="p-6">
        <h2 className="text-xl font-semibold">What You Get</h2>
        <ul className="list-disc pl-5 text-gray-700 mt-2">
          <li>200-page structured narrative</li>
          <li>Emotional growth storytelling</li>
          <li>Self-reflection prompts</li>
          <li>Realistic transformation journey</li>
        </ul>
      </CardContent>
    </Card>
  </div>

  {/* STRUCTURE */}
  <Card className="rounded-2xl shadow-lg mb-10">
    <CardContent className="p-6">
      <h2 className="text-xl font-semibold">Book Structure</h2>
      <div className="grid md:grid-cols-3 gap-4 mt-4 text-sm">
        <div>
          <strong>Part I</strong>
          <p>The Beginning</p>
        </div>
        <div>
          <strong>Part II</strong>
          <p>The Unraveling</p>
        </div>
        <div>
          <strong>Part III</strong>
          <p>The Rebuilding</p>
        </div>
      </div>
    </CardContent>
  </Card>

  {/* EMAIL */}
  <Card className="rounded-2xl shadow-lg mb-10">
    <CardContent className="p-6 text-center">
      <h2 className="text-xl font-semibold">Stay Updated</h2>
      <p className="text-gray-600 mt-2 mb-4">
        Join the list for updates and release notifications.
      </p>

      {!subscribed ? (
        <div className="flex gap-2 justify-center">
          <Input
            value={email}
            onChange={(e) => setEmail(e.target.value)}
            placeholder="Email address"
          />
          <Button onClick={handleSubscribe}>Join</Button>
        </div>
      ) : (
        <p className="text-green-600">Subscribed successfully.</p>
      )}
    </CardContent>
  </Card>

  {/* DOWNLOAD */}
  <div className="text-center mb-10">
    <h2 className="text-lg font-semibold">Download Book</h2>
    <Button onClick={handleDownload} className="mt-3">
      Download PDF
    </Button>
  </div>

  {/* CONTACT */}
  <Card className="rounded-2xl shadow-lg mb-10">
    <CardContent className="p-6 text-center">
      <h2 className="text-xl font-semibold">Contact</h2>
      <p className="mt-2">Matshidiso Lebepe</p>
      <p className="text-sm text-gray-500">Email: your-email@example.com</p>
    </CardContent>
  </Card>

  {/* FOOTER */}
  <footer className="text-center text-xs text-gray-400">
    © {new Date().getFullYear()} Matshidiso Lebepe
  </footer>
</div>

); }
