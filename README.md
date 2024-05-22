<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Trump
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Trump will win the U.S. presidential election in 2024, nationalism brings manufacturing and mining jobs back to the U.S. Domestic manufacturing and fossil fuel companies will benefit. Inflation will happen and media companies will flourish in the chaos.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| BA | Boeing will benefit from increased defense spending and potential growth in domestic aerospace manufacturing. | chat_gpt,google |
| CAT | Caterpillar will see increased demand for its construction and mining equipment as domestic manufacturing and mining activities ramp up. | chat_gpt,claude,google |
| CMCSA | Comcast will benefit from increased demand for news and media content in a chaotic political environment. | chat_gpt,claude,google |
| DE | Deere & Company will benefit from increased demand for its construction and mining equipment as domestic activities ramp up. | chat_gpt,claude,google |
| F | Ford Motor Company will benefit from a resurgence in domestic manufacturing and consumer preference for American-made cars. | chat_gpt |
| FOX | Fox Corporation will benefit from increased viewership and advertising revenue in a politically charged environment. | chat_gpt |
| GE | General Electric will benefit from increased demand for its industrial products and services in a resurgent domestic manufacturing sector. | chat_gpt,google |
| GM | General Motors will benefit from policies favoring domestic manufacturing and potentially increased consumer spending on American-made vehicles. | chat_gpt |
| HAL | Halliburton will see increased demand for its oilfield services as domestic fossil fuel production rises. | chat_gpt,claude |
| MRO | Marathon Oil will see increased demand for its oil and gas production services as domestic fossil fuel production rises. | chat_gpt |
| NUE | Nucor Corporation will gain from increased demand for domestically produced steel for manufacturing and construction. | chat_gpt,claude |
| SLB | Schlumberger will see increased demand for its oilfield services as domestic fossil fuel production rises. | chat_gpt,claude |
| T | AT&T will benefit from increased demand for media and communication services in a politically charged environment. | chat_gpt,google |
| UPS | United Parcel Service will benefit from increased domestic manufacturing and shipping activities. | chat_gpt,google |
| VLO | Valero Energy will benefit from increased domestic refining activities and favorable regulatory changes. | chat_gpt |
| XOM | Exxon Mobil will benefit from increased domestic fossil fuel production and favorable regulatory changes. | chat_gpt,claude,google |
| COP | ConocoPhillips is a large independent oil and gas exploration and production company with significant operations in the U.S. They could also benefit from increased domestic fossil fuel focus. | claude,google |
| CVX | Chevron is one of the world's leading integrated energy companies. Increased focus on domestic fossil fuels could benefit Chevron's U.S. operations. | claude,google |
| DIS | Disney is a diversified entertainment company. The prediction suggests media companies could flourish in the anticipated chaos, which could benefit Disney. | claude,google |
| FCX | Freeport-McMoRan is a leading international mining company with significant operations in North America. Increased domestic mining could directly benefit the company. | claude |
| GOOGL | Alphabet, the parent company of Google, is a leading technology company. Its diverse range of services, including YouTube, could potentially benefit from increased online media consumption. | claude,google |
| JNJ | J&J is a major healthcare company. Like P&G, its focus on domestic consumers could make it a stable investment choice in a nationalist economic environment. | claude |
| META | Meta, formerly Facebook, is a leading social media and technology company. Social media usage could potentially increase in a politically charged environment. | claude,google |
| NEM | Newmont is the world's largest gold mining company, with significant operations in the United States. Increased domestic mining could boost their U.S. operations. | claude |
| PG | P&G is a leading consumer goods company. In times of economic nationalism and potential trade disruptions, large domestic consumer goods companies like P&G could be seen as stable investments. | claude |
| X | U.S. Steel is an integrated steel producer with major production operations in the U.S. Like Nucor, they would benefit from increased domestic manufacturing. | claude |
| DJT |  | twitter |
| ETN |  | google |
| LMT |  | google |
| PH |  | google |
| TDG |  | google |
| TT |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/trump/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/trump" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
