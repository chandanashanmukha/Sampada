import React, { useState, useEffect } from 'react';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';
import { Button } from '@/components/ui/button';
import { Slider } from '@/components/ui/slider';
import { ChevronUp, ChevronDown, AlertCircle } from 'lucide-react';

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

  const [suggestions, setSuggestions] = useState([]);
  const [loading, setLoading] = useState(false);

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

          {/* Type Selection */}
          <div className="space-y-2">
            <label className="block text-sm font-medium">Investment Type</label>
            <select 
              className="w-full p-2 border rounded-lg"
              value={investment.type}
              onChange={(e) => setInvestment(prev => ({...prev, type: e.target.value}))}
            >
              <option value="any">Any</option>
              <option value="stocks">Stocks</option>
              <option value="eft">ETF</option>
              <option value="commodity">Commodity</option>
            </select>
          </div>

          {/* Duration Selection */}
          <div className="space-y-2">
            <label className="block text-sm font-medium">Investment Duration</label>
            <select 
              className="w-full p-2 border rounded-lg"
              value={investment.duration}
              onChange={(e) => setInvestment(prev => ({...prev, duration: e.target.value}))}
            >
              <option value="anytime">Anytime</option>
              <option value="1hour">1 Hour</option>
              <option value="6hours">6 Hours</option>
              <option value="12hours">12 Hours</option>
              <option value="1day">1 Day</option>
              <option value="2days">2 Days</option>
              <option value="1week">1 Week</option>
              <option value="2weeks">2 Weeks</option>
              <option value="1month">1 Month</option>
              <option value="6months">6 Months</option>
              <option value="1year">1 Year</option>
            </select>
          </div>

          {/* Risk Level */}
          <div className="space-y-2">
            <label className="block text-sm font-medium">Risk Level</label>
            <div className="flex space-x-4">
              {['low', 'medium', 'high'].map((level) => (
                <button
                  key={level}
                  className={`flex-1 py-2 px-4 rounded-lg border transition-colors ${
                    investment.risk === level 
                      ? 'bg-purple-600 text-white' 
                      : 'bg-white hover:bg-purple-50'
                  }`}
                  onClick={() => setInvestment(prev => ({...prev, risk: level}))}
                >
                  {level.charAt(0).toUpperCase() + level.slice(1)}
                </button>
              ))}
            </div>
          </div>

          {/* Field Selection */}
          <div className="space-y-2">
            <label className="block text-sm font-medium">Investment Field</label>
            <select 
              className="w-full p-2 border rounded-lg"
              value={investment.field}
              onChange={(e) => setInvestment(prev => ({...prev, field: e.target.value}))}
            >
              <option value="any">Any</option>
              <option value="healthcare">Healthcare</option>
              <option value="motor">Automotive</option>
              <option value="crypto">Cryptocurrency</option>
              <option value="tech">Technology</option>
              <option value="energy">Energy</option>
            </select>
          </div>

          {/* Choose Option */}
          <div className="space-y-2">
            <label className="block text-sm font-medium">Investment Strategy</label>
            <div className="flex space-x-4">
              {['single', 'multiple'].map((option) => (
                <button
                  key={option}
                  className={`flex-1 py-2 px-4 rounded-lg border transition-colors ${
                    investment.choose === option 
                      ? 'bg-purple-600 text-white' 
                      : 'bg-white hover:bg-purple-50'
                  }`}
                  onClick={() => setInvestment(prev => ({...prev, choose: option}))}
                >
                  {option.charAt(0).toUpperCase() + option.slice(1)}
                </button>
              ))}
            </div>
          </div>

          {/* Expected Returns */}
          <div className="space-y-2">
            <label className="block text-sm font-medium">Expected Returns</label>
            <div className="flex items-center space-x-4">
              <div className="flex-1 p-3 bg-white rounded-lg border flex items-center justify-between">
                <span className="text-xl font-bold">${investment.expectedReturns.toLocaleString()}</span>
                <div className="flex flex-col">
                  <Button 
                    variant="ghost" 
                    size="sm"
                    onClick={() => handleReturnsChange('up')}
                  >
                    <ChevronUp className="h-4 w-4" />
                  </Button>
                  <Button 
                    variant="ghost" 
                    size="sm"
                    onClick={() => handleReturnsChange('down')}
                  >
                    <ChevronDown className="h-4 w-4" />
                  </Button>
                </div>
              </div>
            </div>
          </div>

          <Button 
            className="w-full bg-purple-600 hover:bg-purple-700 text-white py-3 rounded-lg text-lg"
            onClick={() => {}}
          >
            Get Investment Suggestions
          </Button>
        </CardContent>
      </Card>
    </div>
  );
};

export default SampadaInvestment;