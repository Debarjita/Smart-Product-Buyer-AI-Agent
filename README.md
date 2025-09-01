# Smart Product Buyer AI Agent 🚗

An intelligent car buying assistant powered by LangGraph and OpenAI that helps users make informed purchasing decisions through automated web scraping, intelligent filtering, and comprehensive market analysis.

## 🌟 Features

- **Conversational Interface**: Natural language interaction to understand user requirements
- **Intelligent Filtering**: Dynamic filter creation based on user preferences
- **Web Scraping**: Automated car listing retrieval from AutoTrader
- **Market Analysis**: Real-time research on car reliability and common issues
- **Detailed Insights**: Comprehensive summaries and recommendations
- **Extensible Design**: Easily adaptable to other platforms and product categories

## 🏗️ Architecture

The agent follows a structured workflow using LangGraph's state management:

1. **User Need Assessment** - Gathers requirements and preferences
2. **Filter Building** - Constructs search parameters
3. **Listing Retrieval** - Scrapes relevant car listings
4. **Analysis & Insights** - Provides market research and recommendations

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- OpenAI API key
- Jupyter Notebook or Google Colab

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/Debarjita/smart-car-buyer-agent.git
cd smart-car-buyer-agent
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
playwright install
patchright install chromium
```

3. **Set up environment variables:**
```bash
cp .env.example .env
# Add your OPENAI_API_KEY to .env file
```

### Quick Start

1. **Run in Jupyter Notebook:**
   - Open `car_buyer_agent.ipynb`
   - Execute all cells
   - Follow the Gradio interface link

2. **Run without GUI:**
   - Set `USE_GRADIO = False` in the notebook
   - Execute cells for command-line interaction

## 📋 Requirements

```
langgraph==0.2.28
langchain==0.3.1
langchain-openai==0.2.1
langchain-community==0.3.0
python-dotenv==1.0.0
playwright==1.47.0
patchright==1.16.0
lxml==5.3.0
nest-asyncio==1.6.0
duckduckgo-search==6.2.13
gradio==4.44.0
```

## 🛠️ Configuration

### Environment Variables

Create a `.env` file with:
```
OPENAI_API_KEY=your_openai_api_key_here
LANGCHAIN_API_KEY=your_langchain_api_key_here  # Optional
```

### Usage Settings

- `USE_GRADIO = True`: Web-based interface
- `USE_GRADIO = False`: Command-line interface

## 🎯 How It Works

### 1. User Interaction
The agent starts by asking about your car preferences:
- Budget range
- Intended usage (commuting, family trips)
- Size preferences
- Special features or constraints

### 2. Smart Filtering
Based on your requirements, it automatically:
- Builds search filters for AutoTrader
- Constructs optimized query URLs
- Applies intelligent parameter mapping

### 3. Data Collection
- Scrapes car listings using Playwright
- Extracts detailed information (price, mileage, features)
- Handles dynamic content loading

### 4. Analysis & Recommendations
- Researches car reliability using web search
- Identifies common issues for specific models
- Provides personalized recommendations

## 🔧 Extending the Agent

### Adding New Platforms

1. Create a new scraper class inheriting from `WebsiteInterface`:
```python
class NewPlatformInterface(WebsiteInterface):
    def __init__(self):
        self.base_url = "https://newplatform.com"
    
    async def crawl(self):
        # Implement scraping logic
        pass
    
    def get_filters_info(self):
        # Return filter information
        pass
```

2. Add it to the web interfaces list:
```python
web_interfaces=[AutotraderInterface(), NewPlatformInterface()]
```

## 📱 Example Output

```
🤖 Car Buyer Assistant: Hi! I'm here to help you find the perfect car. 
What are you looking for in terms of:
- Budget range
- Intended use (daily commuting, family trips, etc.)
- Size preferences
- Any specific features?

👤 User: I need a reliable SUV under $25,000 for family trips

🤖 Assistant: Building filters based on your needs...
Successfully set filters for: AutotraderInterface
Updated URL: https://www.autotrader.com/cars-for-sale/all-cars/cars-under-25000?makeCode=HONDA&makeCode=TOYOTA&vehicleStyleCode=SUVCROSS

Found 15 listings matching your criteria:

1. 2018 Honda CR-V EX - $22,995 - 45,000 miles
   Dealer: Metro Honda
   [Additional details and analysis...]
```

## ⚠️ Important Notes

- **Performance**: Best performance on macOS/Linux. Windows users should use WSL
- **Rate Limits**: Respects website rate limits and robots.txt
- **Legal Compliance**: Only scrapes publicly available data
- **API Usage**: Monitor OpenAI API usage for cost management

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Troubleshooting

### Common Issues

**Gradio interface not loading:**
- Check if all dependencies are installed
- Ensure ports are not blocked
- Try setting `USE_GRADIO = False` for debugging

**Scraping errors:**
- Verify internet connection
- Check if AutoTrader is accessible
- Update Playwright browsers: `playwright install`

**API errors:**
- Verify OpenAI API key is valid
- Check API quotas and billing
- Ensure environment variables are set correctly

## 🙏 Acknowledgments

- Built with [LangGraph](https://github.com/langchain-ai/langgraph) for state management
- Uses [Playwright](https://playwright.dev/) for web scraping
- Powered by [OpenAI](https://openai.com/) for intelligent processing
- Inspired by the GenAI_Agents tutorial collection

---

**⭐ Star this repository if you found it helpful!**
