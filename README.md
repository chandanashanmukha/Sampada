# Sampada AI Investment Advisor 💰
🚀 A smart AI-powered investment advisor that helps users find the best investment options based on their preferences.

## 🌟 Live Demo
🔗 [Try It Here](https://github.com/chandanashanmukha/Sampada)

## 🎯 Features
✅ Personalized investment suggestions  
✅ AI-powered risk analysis  
✅ Easy-to-use interface  

## 🚀 How It Works?
1. Enter your investment details (amount, risk level, duration).
2. Click **"Get Investment Suggestions"**.
3. AI suggests the best investment options based on your input.

## 📸 Screenshots

### Investment Preferences
![Investment Preferences](https://github.com/chandanashanmukha/Sampada/blob/main/screenshot1.jpeg)

### Personalized Suggestions
![Personalized Suggestions](https://github.com/chandanashanmukha/Sampada/blob/main/WhatsApp%20Image%202025-01-29%20at%203.22.22%20PM.jpeg?raw=true)

## 🛠️ Build Output
The output of the build file is a responsive and interactive web application that allows users to input their investment preferences and receive personalized suggestions. Below is a snippet of the main component:

```tsx
import React, { useState } from 'react';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';
import { Button } from '@/components/ui/button';
import { ChevronUp, ChevronDown } from 'lucide-react';

const SampadaInvestment = () => {
  const [investment, setInvestment] = useState({
    amount: 1000,
    type: 'any',
    duration: 'anytime',
    risk: 'low',
    field: 'any',
    choose: 'single',
    expectedReturns: 1200
  });

  const handleAmountChange = (type) => {
    setInvestment(prev => ({
      ...prev,
      amount: type === 'up' ? prev.amount + 100 : Math.max(100, prev.amount - 100)
    }));
  };

  const handleReturnsChange = (type) => {
    setInvestment(prev => ({
      ...prev,
      expectedReturns: type === 'up' ? prev.expectedReturns + 100 : Math.max(prev.amount, prev.expectedReturns - 100)
    }));
  };

  return (
    <div className="max-w-3xl mx-auto p-4 bg-gray-50">
      <Card className="shadow-lg">
        <CardHeader className="bg-purple-600 text-white">
          <CardTitle className="text-2xl font-bold">Sampada AI Investment Advisor</CardTitle>
          <p className="text-purple-100">Get personalized investment suggestions based on your preferences</p>
        </CardHeader>
        
        <CardContent className="space-y-6 p-6">
          {/* Amount Input */}
          <div className="space-y-2">
            <label className="block text-sm font-medium">Investment Amount</label>
            <div className="flex items-center space-x-4">
              <div className="flex-1 p-3 bg-white rounded-lg border flex items-center justify-between">
                <span className="text-xl font-bold">${investment.amount.toLocaleString()}</span>
                <div className="flex flex-col">
                  <Button 
                    variant="ghost" 
                    size="sm"
                    onClick={() => handleAmountChange('up')}
                  >
                    <ChevronUp className="h-4 w-4" />
                  </Button>
                  <Button 
                    variant="ghost" 
                    size="sm"
                    onClick={() => handleAmountChange('down')}
                  >
                    <ChevronDown className="h-4 w-4" />
                  </Button>
                </div>
              </div>
            </div>
          </div>

          {/* Other input fields and buttons */}
        </CardContent>
      </Card>
    </div>
  );
};

export default SampadaInvestment;
