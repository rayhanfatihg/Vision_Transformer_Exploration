# Vision Transformer Exploration

Proyek ini bertujuan untuk mengeksplorasi performa model Vision Transformer (ViT) dan Swin Transformer dalam tugas klasifikasi gambar. Repository ini menyediakan kode untuk pelatihan model, proses pengambilan data uji, serta pengujian model terlatih menggunakan file `.pth`.



Clone repository

git clone https://github.com/rayhanfatihg/Vision_Transformer_Exploration.git

cd Vision_Transformer_Exploration

Install semua library yang dibutuhkan
Jika tersedia, jalankan:

pip install torch torchvision numpy pandas matplotlib opencv-pythonscikit-learn transformerstqdm

(Disarankan menggunakan Python 3.11 dan environment virtual / venv.)

Run modelloader.ipynb untuk melatih model Transformer

Buka modelloader.ipynb di Jupyter Notebook / JupyterLab.

Jalankan cell secara berurutan untuk: load dataset training, setup augmentasi, inisialisasi model (ViT & Swin), fine-tune, dan menyimpan model .pth.

File model yang dihasilkan akan tersimpan ke folder models/ (sesuaikan path di notebook jika berbeda).

Jalankan scrape_images.py untuk memperoleh gambar testing beserta dataset CSV

Pastikan koneksi internet aktif.

Perintah: python scrape_images.py

Output: folder berisi gambar hasil scraping dan file CSV (mis. dataset_test.csv) yang memuat filename + label metadata. Gunakan CSV ini untuk membuat test dataset loader.

Jalankan swin_test.ipynb dan ViT_test.ipynb untuk mengetes model yang telah dilatih (.pth)

Buka swin_test.ipynb untuk menguji Swin; buka ViT_test.ipynb untuk menguji ViT.

Di dalam kedua notebook, periksa variabel model_path atau weights dan sesuaikan dengan nama file .pth terbaru (mis. models/vit_latest.pth atau models/swin_latest.pth).

Jalankan semua cell untuk menghasilkan: prediksi, confusion matrix, classification report (precision/recall/f1)

Catatan Teknis dan Praktis

Pastikan dataset training sudah terstruktur (opsional: folder per kelas atau CSV yang sesuai dengan Dataset class` yang ada di kode).

Untuk training, sangat direkomendasikan menggunakan GPU (CUDA) agar proses lebih cepat. Jika menggunakan CPU, expect training jauh lebih lama.

Sebelum menjalankan testing notebook, selalu ganti model_path di notebook sesuai lokasi .pth terbaru.

scrape_images.py menghasilkan file CSV; verifikasi kolom CSV sesuai format dataloader (mis. kolom filename dan label).
