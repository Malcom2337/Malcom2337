import React from "larondo"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input"; import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";

export default function LarondoHub() { return ( <div className="min-h-screen bg-white text-black p-8"> <header className="text-center mb-12"> <h1 className="text-4xl font-bold text-black shadow-[0_0_10px_red]">LARONDO HUB</h1> <p className="text-red-600 mt-2">Book and Track Helicopter, Train, and Yacht Tickets</p> </header>

<Tabs defaultValue="helicopter" className="max-w-3xl mx-auto">
    <TabsList className="grid grid-cols-3 gap-2 bg-black text-white shadow-[0_0_10px_red]">
      <TabsTrigger value="helicopter">Helicopter</TabsTrigger>
      <TabsTrigger value="train">Train</TabsTrigger>
      <TabsTrigger value="yacht">Yacht</TabsTrigger>
    </TabsList>

    {['helicopter', 'train', 'yacht'].map((mode) => (
      <TabsContent key={mode} value={mode}>
        <Card className="mt-6 shadow-[0_0_10px_red] border-black">
          <CardContent className="p-6">
            <h2 className="text-2xl font-semibold mb-4 text-black">Book Your {mode.charAt(0).toUpperCase() + mode.slice(1)}</h2>
            <form className="grid grid-cols-1 gap-4">
              <Input placeholder="From" className="border-black text-black" />
              <Input placeholder="To" className="border-black text-black" />
              <Input type="date" className="border-black text-black" />
              <Button className="bg-red-600 hover:bg-red-700 text-white">Book Now</Button>
            </form>
          </CardContent>
        </Card>
      </TabsContent>
    ))}
  </Tabs>

  <section className="mt-12 max-w-3xl mx-auto">
    <Card className="shadow-[0_0_10px_red] border-black">
      <CardContent className="p-6">
        <h2 className="text-2xl font-semibold mb-4 text-black">Track Your Ticket</h2>
        <form className="grid grid-cols-1 gap-4">
          <Input placeholder="Enter Booking ID" className="border-black text-black" />
          <Button className="bg-red-600 hover:bg-red-700 text-white">Track</Button>
        </form>
      </CardContent>
    </Card>
  </section>
</div>

); }

