from flask import Flask, request, render_template
import requests
import urllib.parse

app = Flask(__name__)

# RapidAPI Configuration
RAPIDAPI_HOST = "instagram-downloader-download-instagram-videos-stories1.p.rapidapi.com"
RAPIDAPI_KEY = "c61861f807msha2b1fca42798121p1ff20ajsn067d90ecc3c2"  # আপনার API Key এখানে দিন

@app.route("/", methods=["GET", "POST"])
def index():
    if request.method == "POST":
        instagram_url = request.form.get("instagram_url")

        if instagram_url:
            try:
                headers = {
                    "x-rapidapi-host": RAPIDAPI_HOST,
                    "x-rapidapi-key": RAPIDAPI_KEY
                }
                url = f"https://{RAPIDAPI_HOST}/get-info-rapidapi?url={instagram_url}"
                response = requests.get(url, headers=headers)
                response.raise_for_status()  # HTTP error check
                data = response.json()

                if not data.get("error"):
                    download_url = data.get("download_url")
                    thumb_url = urllib.parse.quote(data.get("thumb"), safe=':/')
                    caption = data.get("caption", "No Caption Available")

                    return render_template("index.html",
                                           download_url=download_url,
                                           thumb_url=thumb_url,
                                           caption=caption)
                else:
                    error_message = data.get("message", "ভিডিও খুঁজে পাওয়া যায়নি")
                    return render_template("index.html", error_message=error_message)

            except requests.exceptions.RequestException as e:
                error_message = f"একটি ত্রুটি ঘটেছে: {e}"
                return render_template("index.html", error_message=error_message)
            except (KeyError, TypeError) as e:
                error_message = "ইনস্টাগ্রাম লিঙ্কটি সঠিক নয় অথবা কোনো ভিডিও খুঁজে পাওয়া যায়নি।"
                return render_template("index.html", error_message=error_message)
        else:
            error_message = "অনুগ্রহ করে ইনস্টাগ্রাম লিঙ্ক প্রবেশ করুন।"
            return render_template("index.html", error_message=error_message)

    return render_template("index.html")


if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000, debug=True)
