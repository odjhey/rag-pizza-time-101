# ---- COCO captions (parquet) ----
COCO_FILE := coco-train-00000-of-00001.parquet
COCO_URL  := https://huggingface.co/datasets/sentence-transformers/coco-captions/resolve/main/pair/train-00000-of-00001.parquet

$(COCO_FILE):
	curl -L -C - -o $@ $(COCO_URL)

.PHONY: data-coco
data-coco: $(COCO_FILE)


# ---- ChartQA (parquet) ----
CHARTQA_FILE := chartqa-test-00000-of-00001.parquet
CHARTQA_URL  := https://huggingface.co/datasets/lmms-lab/ChartQA/resolve/main/data/test-00000-of-00001.parquet

$(CHARTQA_FILE):
	curl -L -C - -o $@ $(CHARTQA_URL)

.PHONY: data-chartqa
data-chartqa: $(CHARTQA_FILE)


# ---- @todo Some PDF (single PDF file for testing pipelines) ----


# ---- Convenience targets ----
.PHONY: clean
clean:
	rm -f $(COCO_FILE) $(CHARTQA_FILE) $(PDF_FILE)

